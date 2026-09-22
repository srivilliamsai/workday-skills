# Choosing a Workday API

| Need | API | Sample |
| --- | --- | --- |
| A page needs a few fields in one round trip | Graph | `catalog/vehicleRegistration/presentation/graphQueries` |
| Create or update one resource | REST | `catalog/updateWorkdayAccounts` |
| Bulk XML, or a `Put_` operation | SOAP / WWS | `catalog/workerInboundImageUpload` |
| A report or extract | WQL | `catalog/employeeRecognition/presentation/wqlQueries` and `catalog/wql` |
| One Graph call that creates a record | Graph | `catalog/createSpotBonus` |

- Always ask for the field set before choosing Graph. Graph is for shaping a response, not for a 50,000-row load.
- Always use SOAP when the operation is a bulk `Put_`. Partition 500 to 1,000 records per envelope.
- Always use WQL when the question is analytical (`COUNT`, `GROUP BY`, custom objects). Do not walk a REST collection to compute a headcount.
- Never call four REST resources from a page when one Graph query returns those fields.
- Never cache a resolved Workday IP. Use the tenant service host.

Tenant-wide REST and Graph traffic is limited to about 100 requests per second. One OAuth client is limited to about 30 requests per second. On `429`, read `X-RateLimit-Remaining` and `X-RateLimit-Reset` and back off. Do not retry immediately.

Active API versions stay available. A deprecated version keeps working for at least 18 months. Put the major version in the path.

Open next: `Documentation/Workday APIs/Workday APIs Overview/Workday APIs Overview.md`
