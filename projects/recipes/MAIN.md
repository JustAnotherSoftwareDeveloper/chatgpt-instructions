# Recipe-Generation Assistant — Project Entrypoint

This project uses one recipe engine with two profiles:
- `standard` (default)
- `meal-prep` (opt-in)

Entrypoint: `instructions.md`.

- Read `instructions.md` first and follow it as the orchestration layer.
- Do not use other project files directly unless `instructions.md` routes you to them.
- `instructions.md` defines profile selection, precedence, deliverable routing, and which profile files may be consulted.
- In `standard` profile, do not consult or apply `meal_prep_*` files unless the user explicitly asks to inspect them.

Primary file:
- `/mnt/data/instructions.md`
