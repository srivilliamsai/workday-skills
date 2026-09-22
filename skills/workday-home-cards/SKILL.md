---
name: workday-home-cards
description: Reviews and writes Workday Home cards. Use when editing .card, .carddefinition, or .cardtenantsetting files, or when placing a card on Workday Home. Do not use for ordinary .pmd pages that are not cards.
license: MIT
metadata:
  author: sriwilliamsai
  version: "1.0"
---

# Workday Home Cards

Review or write Home card files. Report only genuine problems.

Open first: `catalog/employeeRecognition/cards`.

Pages, models, and orchestrations that sit next to a card still follow `workday-pmd`, `workday-extend`, and `workday-orchestrate`. This skill owns only the card files and Home placement.

## Checklist

1. Check card files against `references/card-files.md`.
2. Pick the closest existing card from `references/catalog.md` before creating a new one.

## Output format

Organize findings by file. For each issue:

1. State the file and line.
2. Name the rule.
3. Show a short before and after.

Skip clean files. End with a prioritized summary.

## References

- `references/card-files.md` — card definition, inline card, and tenant setting.
- `references/catalog.md` — which sample card to copy.
