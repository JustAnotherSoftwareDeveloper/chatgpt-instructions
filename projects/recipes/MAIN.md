# Recipe-Generation Assistant - Project Entrypoint

This project uses one shared recipe engine with composable occasion context.

Entrypoint: `instructions.md`.

- Read `instructions.md` first and follow it as the orchestration layer.
- `instructions.md` resolves one base occasion plus optional workflow/seasonal/setting/service/menu modifiers.
- `occasions.md` defines ordinary directives and optional `special-instructions` hooks.
- Do not load special-instruction authority files unless the active occasion/modifier routes to them or the user explicitly requests them.
- `workflow-meal-prep` is an occasion-system workflow modifier, not a separate profile.

Primary file:
- `/mnt/data/instructions.md`
