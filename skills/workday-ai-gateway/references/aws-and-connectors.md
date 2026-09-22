# AWS connectors

The path is Extend page, then Orchestrate, then AWS. Do not call Rekognition, Textract, Translate, or Comprehend from PMD.

- Always sign the outbound request in the orchestration. Store IAM credentials in the tenant secret store. `catalog/AWSStarterKit` is the pattern.
- Always restrict the IAM role to the actions that one flow uses.
- Always strip fields the cloud API does not need before the call. A badge photo does not need a national id.
- Badge generation and EventBridge routing live in `catalog/AWSBadgeGenerator`. Do not invent a second event bus in the page.
- Never put a bucket URL, access key, secret key, or webhook in a `.pmd` or `.amd`.
- Never copy an access key into a new file. Point at the tenant secret store.

Open next: `catalog/AWSStarterKit`
