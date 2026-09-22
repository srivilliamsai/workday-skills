---
name: workday
description: Chooses which Workday skill to apply when starting an app or when a task spans more than one artifact. Use when the user asks to build a new Workday app, choose Extend versus an Integration App versus an API, or the change touches pages, models, orchestrations, and queries together.
license: MIT
metadata:
  author: sriwilliamsai
  version: "1.0"
---

# Workday

Pick one skill and one canonical sample. Do not restate that skill's rules. If the task is a single file type, stop and use only the matching skill.

## Decision

| You are building or changing | Skill | Open first |
| --- | --- | --- |
| App shell, AMD, SMD, business object, security domain, business process, manifest, WDCLI, App Hub | `workday-extend` | `catalog/vehicleRegistration` |
| Model plus approval business process | `workday-extend` | `catalog/tuitionReimbursement` |
| `.pmd`, `.script`, charts, `.properties` | `workday-pmd` | `catalog/pmdWidgetDictionary` |
| `.card`, `.carddefinition`, `.cardtenantsetting`, Workday Home | `workday-home-cards` | `catalog/employeeRecognition/cards` |
| `.orchestration`, `.suborchestration`, listeners, integration deploy or monitoring | `workday-orchestrate` | `catalog/orchestrateForIntegrationsSampler` |
| Outbound integration file | `workday-orchestrate` | `catalog/employeeDemographicOutbound` |
| `.graphquery`, `.wqlquery`, REST, SOAP, OAuth, pagination | `workday-apis` | `catalog/vehicleRegistration/presentation/graphQueries` |
| AI Gateway, document intelligence, WQL generation, or an AWS starter call | `workday-ai-gateway` | `catalog/generateWQL` |
| A prompt for the product Workday Developer Copilot | `workday-developer-copilot` | `Documentation/Workday Developer Copilot` |

## Which runtime

- User-facing UI inside Workday: Extend (`workday-extend` plus `workday-pmd`).
- Headless sync, file drop, schedule, or business event: Integration App (`workday-orchestrate`).
- A caller outside Workday reading or writing data: API (`workday-apis`). Graph for a UI that needs an exact field set. REST for one resource. SOAP for bulk XML. WQL for reporting.

## Layout

Match the canonical sample's folders. Do not invent a new tree.

- `presentation/` for `.amd`, `.smd`, `.pmd`, `graphQueries/`, `wqlQueries/`, `scripts/`, `presentationLabels/`, and in-page `.card` files
- `model/` for business objects, security domains, and business processes
- `orchestration/` for flows
- `cards/` at the app root for `.carddefinition` and `.cardtenantsetting`
- `attributes/` and `appManifest.json` at the app root

Copy only apps under `catalog/`. Do not invent security domain ids, routes, or endpoints.
