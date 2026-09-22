# Extend model

Match `Vehicle.businessobject` and `EducationAssistanceApproval.businessprocess`. The docs use `STRING` and `REFERENCE`. Catalog apps use `TEXT` and `SINGLE_INSTANCE`. Follow the catalog file you are editing.

## Business object

- Always include `name`, `label`, `defaultSecurityDomains`, `defaultCollection`, and `fields`.
- Always set `defaultCollection.name` to a plural camelCase collection, with `label` and `description`.
- Always give one field `useForDisplay: true` and `isReferenceId: true` when the object needs a human key. Vehicle uses `licensePlate`.
- Always use catalog field types: `TEXT`, `INTEGER`, `DATE`, `BOOLEAN`, `DECIMAL`, `SINGLE_INSTANCE`.
- Always set `DATE` precision to `"DAY"` unless the sample you are copying uses another precision.
- Always set `DECIMAL` scale with `decimals`. Tuition reimbursement uses `decimals: 2` on `requestAmount`.
- Always point a worker or location reference at `target` (`WORKER`, `LOCATION`) and set `secureByTarget: true` on worker ownership fields.
- Always add `label` and `description` on every field.
- Never use `STRING`, `REFERENCE`, or `primaryKey` in a catalog-style object. Those names are from the short doc sample only.
- Never add `required: true` to a field on an object that already has rows unless a migration plan exists. Nullable additions can ship anytime. Required additions cannot.
- Put derived display text in `derivedFields` with an `expression`. Do not store a second copy of `year + make + model` as a normal field.

## Business process

Match Tuition Reimbursement:

- Always set `targetBusinessObject` to the business object `name`.
- Always list approval `actions` from `APPROVE`, `DENY`, and `SEND_BACK` only.
- Always give `approvalStep.pageRoute`, `details.pageRoute`, each `actionSteps[].pageRoute`, and `revisePageRoute` a path that includes the event id (`{eventId}` or `{eventStepId}`).
- Never point a business process route at a page the AMD does not register.

## Retention

- Custom object rows live in the tenant. Purge them with Maintain Custom Object Retention Policies. Do not invent a delete-on-deploy flag.

Open next: `catalog/vehicleRegistration/model/Vehicle.businessobject`
