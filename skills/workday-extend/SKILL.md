---
name: workday-extend
description: Reviews and writes Workday Extend app shells and data models. Use when editing .amd, .smd, .businessobject, .businessprocess, .securitydomain, .attachment, or appManifest.json, or when using WDCLI, App Hub, or tenant promotion. Do not use for .pmd pages, .card files, or .orchestration flows.
license: MIT
metadata:
  author: sriwilliamsai
  version: "1.0"
---

# Workday Extend

Review or write the Extend app shell and model. Report only genuine problems.

Open first: `catalog/vehicleRegistration`. For a business process, also open `catalog/tuitionReimbursement`.

If the file is `.pmd`, `.script`, `.properties`, `.card`, `.carddefinition`, `.cardtenantsetting`, or `.orchestration`, stop. Those belong to `workday-pmd`, `workday-home-cards`, or `workday-orchestrate`.

## Checklist

1. Check the app shell against `references/app-shell.md`.
2. Check business objects and business processes against `references/model.md`.
3. Check security domains and page or object domain names against `references/security.md`.
4. Check versioning, promotion, and local commands against `references/lifecycle.md`.

Match the sample folders: `presentation/` for `.amd` and `.smd`, `model/` for objects and security domains. Do not invent routes, security domain ids, or endpoints.

## Output format

Organize findings by file. For each issue:

1. State the file and line.
2. Name the rule.
3. Show a short before and after.

Skip clean files. End with a prioritized summary.

## References

- `references/app-shell.md` — AMD tasks, SMD auth and error pages, manifest, data providers.
- `references/model.md` — business object fields and business process routes.
- `references/security.md` — security domains shared by the object and the page.
- `references/lifecycle.md` — WDCLI, App Hub versions, promotion, retirement.
