---
name: workday-orchestrate
description: Reviews and writes Workday Orchestrate and Integration App flows. Use when editing .orchestration or .suborchestration files, listeners, Orchestrate expression language, or integration deployment and monitoring. Do not use for .pmd pages or .amd files.
license: MIT
metadata:
  author: sriwilliamsai
  version: "1.0"
---

# Workday Orchestrate

Review or write orchestration files. Report only genuine problems.

Open first: `catalog/orchestrateForIntegrationsSampler/orchestration/GetWorkers.orchestration`. For a real outbound integration, open `catalog/employeeDemographicOutbound`.

## Checklist

1. Check the file shape against `references/flows.md`.
2. Check expressions against `references/expression-language.md`.
3. Check listeners, steps, and routers against `references/components.md`.
4. Check credentials and ISU access against `references/security.md`.
5. Check retries, deploy, and failures against `references/operations.md`.
6. Pick the closest sample from `references/catalog.md` before writing a new flow.

Do not rewrite a catalog flow into the short documentation JSON (`listener`, `steps`, `REST_INVOKER`). That JSON is the concept map. The files on disk are Maya flows.

## Output format

Organize findings by file. For each issue:

1. State the file and line.
2. Name the rule.
3. Show a short before and after.

Skip clean files. End with a prioritized summary.

## References

- `references/flows.md` — Maya flow shape versus the concept map.
- `references/expression-language.md` — quotes, null safety, and functions.
- `references/components.md` — listeners, steps, routers, suborchestrations.
- `references/security.md` — OAuth, keystores, and ISU scope.
- `references/operations.md` — retry, deploy, and troubleshooting.
- `references/catalog.md` — which integration sample to copy.
