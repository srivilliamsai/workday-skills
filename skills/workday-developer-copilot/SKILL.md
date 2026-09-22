---
name: workday-developer-copilot
description: Shapes prompts for the product Workday Developer Copilot. Use when the user names Workday Developer Copilot and wants a prompt for an Extend model, a PMD page, an orchestration, or an API payload. Do not use for Cursor agent skills or for reviewing application source.
license: MIT
metadata:
  author: sriwilliamsai
  version: "1.0"
---

# Workday Developer Copilot

Write the prompt. Do not review application source here. After Copilot returns JSON, check it with `workday-extend`, `workday-pmd`, or `workday-orchestrate`. Copilot's own examples use a short page shape that does not match catalog `.pmd` files.

## Checklist

1. Shape the prompt with `references/prompts.md`.
2. Apply `references/privacy.md` before anything is pasted into Workday Developer Copilot.

## Output format

Return one prompt the user can paste, then a short list of what you left out under privacy. Do not invent tenant data to fill the prompt.

## References

- `references/prompts.md` — what a Workday Developer Copilot prompt must name.
- `references/privacy.md` — what must not be pasted.
