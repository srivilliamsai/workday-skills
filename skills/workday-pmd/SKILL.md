---
name: workday-pmd
description: Reviews and writes Workday Extend presentation files. Use when editing .pmd pages, .script files, chart pages, or .properties localization bundles. Do not use for .card, .carddefinition, .cardtenantsetting, .amd, or .orchestration files.
license: MIT
metadata:
  author: sriwilliamsai
  version: "1.0"
---

# Workday PMD

Review or write pages, scripts, charts, and localization. Report only genuine problems.

Open first: `catalog/pmdWidgetDictionary`. For scripts, open `catalog/pmdScripting`. For charts, open `catalog/chartDictionary`.

Card files belong to `workday-home-cards`. AMD, SMD, and business objects belong to `workday-extend`.

## Checklist

1. Check page shape, endpoints, and bindings against `references/pages.md`.
2. Check widgets against `references/widgets.md`.
3. Check scripts against `references/scripting.md`.
4. Check charts against `references/charts.md`.

Copy widget tags from the dictionary page that already demonstrates them. Do not invent a widget type.

## Output format

Organize findings by file. For each issue:

1. State the file and line.
2. Name the rule.
3. Show a short before and after.

Skip clean files. End with a prioritized summary.

## References

- `references/pages.md` — page id, security domains, endpoints, bindings, labels.
- `references/widgets.md` — sections, grids, buttons, and task links.
- `references/scripting.md` — script includes and the export object.
- `references/charts.md` — chart 2.0 tags and their data scripts.
