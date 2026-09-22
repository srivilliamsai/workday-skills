---
name: workday-ai-gateway
description: Reviews Workday AI Gateway calls and the AWS starter pattern shipped in the Workday catalog. Use when editing document intelligence, WQL generation, sentiment analysis, or AWS Translate, Textract, Comprehend, or badge flows. Do not use for ordinary .pmd layout or for prompts to Workday Developer Copilot.
license: MIT
metadata:
  author: sriwilliamsai
  version: "1.0"
---

# Workday AI Gateway

Review Gateway and cloud connector calls. Report only genuine problems.

Open first: `catalog/generateWQL`. For AWS, open `catalog/AWSStarterKit`.

The flow file still follows `workday-orchestrate`. The page still follows `workday-pmd`. This skill owns the Gateway or cloud call.

## Checklist

1. Check the Gateway call against `references/gateway.md`.
2. Check AWS calls against `references/aws-and-connectors.md`.
3. Copy the closest app in `references/catalog.md`.

Never write a secret, tenant URL, or API key into a skill file or a new source file. Point at the sample's secret reference.

## Output format

Organize findings by file. For each issue:

1. State the file and line.
2. Name the rule.
3. Show a short before and after.

Skip clean files. End with a prioritized summary.

## References

- `references/gateway.md` — Gateway capabilities, endpoints, and privacy.
- `references/aws-and-connectors.md` — call AWS from Orchestrate, not from the page.
- `references/catalog.md` — which Gateway or cloud sample to copy.
