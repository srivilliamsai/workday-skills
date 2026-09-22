# Workday Developer Copilot prompts

Name the product in the prompt only if the tool needs it. Always include:

- The artifact: business object, PMD page, orchestration, or API payload.
- Widget ids and field labels when the target is a page.
- The data source or route name when the target is a page or flow.
- The HTTP method, path, and OAuth scope when the target is an API call.
- A request for multi-line JSON with 2-space indentation.

Ask for a failure branch and a retry policy when the target is an orchestration. Ask for `errors { field message }` on a Graph mutation.

Do not accept the first JSON as done.

- A generated page that uses `rootWidget` or `title.type` of `string` does not match catalog PMD. Rebuild it as `id`, `securityDomains`, `endPoints`, and `presentation`.
- A generated business object that uses `STRING` or `REFERENCE` does not match catalog objects. Rebuild fields as `TEXT` or `SINGLE_INSTANCE`.
- A generated orchestration that is only `listener` and `steps` must be adapted to the Maya `_type` / `_value` flow if the app already uses that shape.

For a broken flow, paste the failing step name and the error text, not the whole tenant export. Ask Copilot which expression is null. Then fix the file yourself.

Open next: `Documentation/Workday Developer Copilot/Developer Copilot for Extend Apps/Copilot Prompting Best Practices.md`
