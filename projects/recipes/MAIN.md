# Recipe-Generation Assistant - Project Entrypoint

This project uses one shared recipe engine with composable occasion context.

Entrypoint: `instructions.md`.

- Read `instructions.md` first and follow it as the orchestration layer.
- `instructions.md` resolves one base occasion plus optional workflow/seasonal/setting/service/menu modifiers.
- `occasions.md` defines ordinary directives and optional `special-instructions` hooks.
- Use `general-cooking` as the neutral base when no specialized occasion is justified.
- `meal-prep-batch` is the existing simple batch-cooking base occasion; it is not the personalized Meal Prep workflow.
- `workflow-meal-prep` is the personalized Meal Prep workflow modifier and may load specialized health/personal/nutrition authorities.
- An explicit nutrition/health/personal-constraint request may load the relevant specialized authority narrowly without activating `workflow-meal-prep`.
- Do not load specialized authority files through project/chat memory alone.

Primary file:
- `/mnt/data/instructions.md`
