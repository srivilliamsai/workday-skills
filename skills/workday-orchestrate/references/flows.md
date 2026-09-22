# Orchestration flows

Catalog flows are Maya documents. `GetWorkers.orchestration` and `EmployeeDemographicFull.orchestration` both start like this:

- `flowVersion` (these samples use `"3.3.0"`).
- `_type`: `"Flow"`.
- `_value.name._type`: `"Identifier"`.
- `_value.type._value`: a `FlowType` such as `.maya.IntegrationFrameworkTrigger`.
- `_value.start` and `_value.end`.

Rules:

- Always preserve `flowVersion`, `_type`, and `_value` when editing a sample. Add a step by cloning a nearby step in the same file.
- Always keep the flow `name` equal to the file name without `.orchestration`.
- Never replace a Maya flow with the documentation's simplified object (`listener.type`, `steps[].type` of `REST_INVOKER`, `DATA_MAPPER`, `TRY_CATCH`). Use that simplified model only to decide what the flow must do, then implement it in the Maya shape the file already uses.
- Never change `flowVersion` unless the file you are copying already uses the new version.
- Never invent a new top-level key the surrounding steps do not use.

Concept map, in order: inbound listener, context, processing steps, optional router, response or end. Synchronous Extend calls set the execution mode to synchronous and return before the page renders. See `Documentation/Extend Apps/Extend App Development/Creating Synchronous Orchestrations.md`.

Open next: `catalog/orchestrateForIntegrationsSampler/orchestration/GetWorkers.orchestration`
