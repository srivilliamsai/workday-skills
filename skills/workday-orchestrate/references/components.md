# Orchestration components

Use these listener types. Pick the one that matches the trigger. Do not add a second listener for the same event.

| Type | Use |
| --- | --- |
| `HTTP` | Real-time inbound call |
| `SCHEDULED_TRIGGER` | Cron or interval batch |
| `WORKDAY_EVENT_LISTENER` | Hire, terminate, or other business event |
| `SFTP_POLLER` | File drop from a carrier or bank |

Step types from the component reference. Implement them as Maya steps in the file you are editing:

- `REST_INVOKER` needs `url` or `endpoint`, `method`, and a timeout.
- `SOAP_INVOKER` needs `wsdl`, `operation`, and the envelope.
- `DATA_MAPPER` writes one output document from context.
- `VALIDATOR` checks JSON Schema or XSD and sets `failOnError`.
- `ROUTER` has `conditions` plus a `defaultBranch`. Country and status branches always need the default.
- `FOREACH` names the `collection`. Set `batchSize` when the collection is large.
- `SUBORCHESTRATION_INVOKER` names `targetOrchestration`, `executionMode` (`SYNCHRONOUS` when the parent needs the result), `inputParameters`, and `outputVariable`.

A suborchestration runs in its own frame. Unhandled errors there must not commit the parent. Test it with mock input before wiring it in.

Character maps and text templates stay in the orchestration that already uses them. Do not add a new template format.

Open next: `Documentation/Integration Apps/Integration App Components Reference/Orchestration Steps Reference.md`
