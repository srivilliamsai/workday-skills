# REST

- Always get a token with the client-credentials grant. Send it as `Authorization: Bearer`. Tokens in the overview expire in 3600 seconds. Refresh on `401`. Do not reuse an expired token.
- Never write `client_id`, `client_secret`, or the access token into a source file. The documentation curl sample uses placeholders. Keep them as placeholders.
- Always page with `limit` (default 20, maximum 100) and `offset`. Sort with `sortBy` and `asc` or `desc`.
- Always filter with the documented form, for example `hireDate gt '2026-01-01'`.
- Always branch on status: `200` read, `201` created, `400` fix the body, `403` fix the domain or ISU, `404` bad id, `429` back off, `500` retry with the orchestration retry policy.
- Always include the major version in the path: `/ccx/api/v1/{tenant}/...`. Worker, job, organization, compensation, and time-tracking resources live under that prefix. Do not invent a resource name that is not in the API catalog or the sample you opened.
- Never log the token or the request body when it contains pay or government identifiers.

AMD data providers already point at `{{apiGatewayEndpoint}}/common/v1/`, `/staffing/v1/`, and `/wql/v1/`. Reuse those keys from the page. Do not add a second absolute host.

Open next: `Documentation/Workday APIs/Workday REST APIs/Error Handling and Status Codes.md`
