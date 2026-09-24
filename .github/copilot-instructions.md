# GitHub Copilot Instructions — chatgpt-instructions repo

## What this repo is

This repo holds instruction sets for ChatGPT (and similar AI) projects. Each folder under `projects/` is one self-contained project. The files inside are markdown documents that tell an AI how to behave — what to research, what to output, and in what order.

These are **not application code**. There is no build step, no tests, and no runtime. The "correctness" of a file is whether an AI following it produces the right output.

---

## Project anatomy (mandatory reading before editing any file)

Every project follows the same two-layer pattern:

```
projects/<project-name>/
  MAIN.md            ← pointer only; routes to instructions.md
  instructions.md    ← orchestrator / thin glue layer
  <authority>.md     ← canonical files (each owns one responsibility)
  <template>.md      ← output format contracts
```

### Layer 1 — MAIN.md
A single-purpose pointer. It names the entry point (`instructions.md`) and nothing else. Do not add logic, rules, or routing here. If the project uses a non-standard filename (e.g. `healthy_instructions.md`), MAIN.md names that file.

### Layer 2 — instructions.md (orchestrator)
The thin glue layer. Its only jobs are:
- List the canonical authority files and their single responsibilities.
- Define a precedence order for resolving conflicts between authority files.
- Implement routing rules (which user request triggers which output workflow).
- Set global defaults that belong to no single authority.

It must **not** restate rules that already live in an authority file. It delegates, routes, and references — it does not duplicate.

### Authority files
Each authority file owns one topic domain and is the single source of truth for that domain. Examples:
- `meal_sources.md` — research and sourcing protocol
- `occasions.md` — occasion taxonomy and directives
- `options.md` — options-stage output interface
- `recipe_template.md` — final recipe output format
- `revisions.md` — post-cook diagnosis and correction workflow
- `equipment.md` — equipment inventory and fit rules
- `audit.md` — audit workflow and issue reporting
- `reviews.md` — review interpretation and manipulation detection
- `research_sources.md` — evidence admissibility and weighting
- `seller_instructions.md` — seller/channel evaluation

Authority files must not duplicate rules from sibling authority files. If file A needs B's behavior, it references B by name — it does not restate B's rules inline.

### Template files
Template files define output format contracts (required sections, ordering, required fields). They are referenced by the orchestrator and authority files. They do not contain workflow logic.

---

## Editing conventions

### No-duplication rule (most important)
Before adding a rule to any file, identify which file already owns that topic domain. Add the rule there. If the rule spans multiple domains, add it to `instructions.md` as a routing/default, then reference the relevant authority files from there.

Violation pattern to avoid: copying a sourcing rule into `options.md` when `meal_sources.md` already owns sourcing.

### Precedence must be explicit
`instructions.md` must contain a precedence section that resolves authority collisions. When you edit the orchestrator, keep the precedence list accurate. When you add a new authority file, add it to the precedence list in the correct position.

### Routing rules must be exhaustive and deterministic
Routing in `instructions.md` must cover all trigger phrases for every deliverable. Use first-match logic (the first matching rule wins). When adding a new deliverable type, add its trigger phrases and output target to the routing section.

### File references use relative paths or named references
Within a project, files reference each other by filename or relative path. Do not use absolute paths unless the project's instructions.md already establishes one (some projects use `/mnt/data/` paths for ChatGPT uploads). Match the existing convention in the project you are editing.

### Versioning / date prefixes
Some files carry a date prefix in their internal `#` header (e.g. `# 20260115_instructions.md`). This is a content-revision marker, not the filename. When making significant changes to an already-dated file, update the date prefix in the header to reflect the current date. Do not rename the file itself.

---

## Adding a new project

1. Create `projects/<project-name>/` with at minimum:
   - `MAIN.md` — pointer to `instructions.md`
   - `instructions.md` — orchestrator with canonical file map, precedence, routing, and global defaults
2. Add authority files for each distinct responsibility.
3. Add template files for each distinct output format.
4. Every authority file must be listed in `instructions.md`'s canonical file map with its single responsibility and no-duplication boundary stated.

---

## Adding a new authority file to an existing project

1. Create the file with a clear single-responsibility statement at the top.
2. Add it to `instructions.md`'s canonical file map section: name, role, dependencies (if any), and boundary (what must not be restated elsewhere).
3. Add it to the precedence list in the correct position.
4. If an existing authority file currently contains rules that belong to the new file, move those rules and replace them with a reference.

---

## Adding a new output workflow (deliverable type)

1. Create or update the authority file(s) that define the workflow logic.
2. Create or update the template file that defines the output format.
3. Add a routing rule to `instructions.md` with trigger phrases and the target template.
4. Add the new file(s) to `instructions.md`'s canonical file map and precedence list.
5. Add the workflow reference to `MAIN.md` only if the project's MAIN.md pattern calls for listing workflows — most do not.

---

## Upgrading existing projects

### Modifying rules in an existing authority file
1. Read the file in full before editing to understand its current scope.
2. Check sibling files for any rules that already depend on or reference the section you are changing. Update those references if the rule's name, location, or semantics change.
3. If you are adding a new rule: confirm the owning file is correct (not `instructions.md` or a sibling authority file).
4. If you are tightening or relaxing an existing rule: state the change explicitly in the file — do not silently overwrite a rule with an incompatible replacement.
5. If the file has a date prefix in its internal header (e.g. `# 20260115_authority.md`), update the date to today's date after making significant changes. Do not rename the file itself.
6. After editing, re-read `instructions.md` to verify the canonical file map entry and precedence position still describe the file accurately.

### Removing or deprecating a rule from an authority file
1. Search sibling files and `instructions.md` for any reference to the rule being removed. Update or remove those references.
2. If the rule is being moved to a different file, replace the original with a one-line reference to the new owner — do not leave a silent gap.
3. Do not leave orphaned references in `instructions.md` that point to rules that no longer exist.

### Splitting an authority file that has grown too large
1. Identify the two (or more) distinct responsibilities the file has accumulated.
2. Create a new authority file for the secondary responsibility, following the single-responsibility pattern (open with a role statement, end with a boundary statement).
3. Move the relevant rules to the new file; replace them in the original with a named reference.
4. Update `instructions.md`: add the new file to the canonical file map and the precedence list in the correct position.
5. Check all other files that referenced the old authority file to see if any of those references now need to point to the new file instead.

### Upgrading a template file
1. Template files define format contracts. Only add, change, or remove sections that reflect a real change in the deliverable structure.
2. If a section addition requires a new decision rule (e.g. "omit when X"), add that rule to the owning authority file — not to the template.
3. After changing a template, verify that all authority files and `instructions.md` that reference it still describe it correctly.

### Upgrading instructions.md (orchestrator)
1. The orchestrator must stay thin. If an edit causes you to write domain logic, stop and put that logic in the appropriate authority file instead.
2. When adding to the canonical file map, include: file name, single responsibility, and the no-duplication boundary.
3. When adding to the precedence list, place the new entry in an intentional position and verify there are no new collisions with existing entries.
4. When adding routing rules, follow first-match order: more specific trigger phrases before general ones. Verify new triggers do not shadow existing ones unintentionally.

### Adding a net-new file to an existing project
Follow the steps in "Adding a new authority file to an existing project" or "Adding a new output workflow" above. After adding the file:
- Verify `instructions.md`'s canonical file map is updated.
- Verify `instructions.md`'s precedence list is updated.
- Verify no existing file now needs to cede rules to the new file (if so, move them and replace with a reference).

---

## Editing rules for specific common files

### instructions.md
- Keep it thin. If you are writing more than a few sentences of domain logic (sourcing rules, formatting rules, diagnosis steps), that logic belongs in an authority file, not here.
- The canonical file map section must stay complete. Every authority and template file must be listed.
- The precedence section resolves conflicts. Every authority file must appear in it.
- The routing section is deterministic. Trigger phrases must not overlap across workflows unless the first-match rule resolves the ambiguity cleanly.

### MAIN.md
- One job only: name the entry point. Do not add routing logic, rules, or workflow descriptions.
- Acceptable content: a one-line role statement, the entry point file name, and a brief instruction to read that file first.

### Template files
- Define output format (required sections, order, required fields, formatting rules).
- Do not contain workflow logic, sourcing rules, or routing logic. Those belong in authority files and the orchestrator.
- If a template section requires a decision (e.g. "omit this section if no-browse"), the decision rule lives in the authority file; the template only specifies the section structure.

### Authority files
- Open with a single-responsibility statement.
- Contain only rules within their domain.
- Reference sibling authority files by name when cross-domain behavior is needed.
- Do not embed routing logic (that is the orchestrator's job).

---

## What Copilot should help with in this repo

- **Drafting new authority files**: follow the single-responsibility pattern; open with a role statement; end with a boundary statement listing what must not be restated elsewhere.
- **Extending instructions.md**: add to the canonical file map and precedence list; do not duplicate authority file logic; keep routing deterministic.
- **Auditing a project for duplication**: compare rules across files and flag content that appears in the wrong owner file.
- **Refactoring an authority file**: if a file has grown to cover multiple responsibilities, propose a split with a new file and update `instructions.md` accordingly.
- **Writing trigger phrases**: make triggers specific enough to avoid ambiguity; use first-match order so more specific triggers come before general ones.
- **Checking precedence lists**: verify every authority file is represented and the ordering is intentional.

---

## What Copilot should NOT do

- Do not add rules to `MAIN.md` beyond the pointer pattern.
- Do not duplicate sourcing rules, formatting rules, or workflow logic across more than one file.
- Do not invent output sections in a template file that are not backed by workflow logic in an authority file.
- Do not add absolute paths unless the existing project already uses them.
- Do not generate actual recipes, shopping recommendations, or other end-user outputs — this repo defines instructions for an AI, not the AI's outputs.
