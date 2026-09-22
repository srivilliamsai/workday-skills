---
name: workday-apis
description: Chooses and reviews Workday REST, SOAP, Graph API, and WQL calls. Use when editing .graphquery or .wqlquery files, or when writing REST, SOAP, OAuth, pagination, or rate-limit handling. Do not use for .pmd layout or .orchestration step structure.
license: MIT
metadata:
  author: sriwilliamsai
  version: "1.0"
---

# Workday APIs

Pick the API, then review the call. Report only genuine problems.

Open `references/choosing-an-api.md` first. Load only the reference for the API you are using.

## Checklist

1. Choose the API with `references/choosing-an-api.md`.
2. For REST, open `references/rest.md`.
3. For SOAP or WWS, open `references/soap.md`.
4. For `.graphquery` or GraphQL, open `references/graph.md`.
5. For `.wqlquery` or WQL, open `references/wql.md`.

Page layout belongs to `workday-pmd`. The Maya flow that sends the call belongs to `workday-orchestrate`.

## Output format

Organize findings by file. For each issue:

1. State the file and line.
2. Name the rule.
3. Show a short before and after.

Skip clean files. End with a prioritized summary.

## References

- `references/choosing-an-api.md` — Graph, REST, SOAP, or WQL.
- `references/rest.md` — OAuth, pages, errors, versions, rate limits.
- `references/soap.md` — WS-Security, WSDL hosts, batch size.
- `references/graph.md` — `.graphquery` files and cursors.
- `references/wql.md` — `.wqlquery` files and data sources.
