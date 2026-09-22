# Extend app shell

Match Vehicle Registration. The AMD reference's `flowDefinitions` example is for a wizard flow only. Do not replace a `tasks` AMD with that example.

## AMD

- Always register each page as a task with `id`, `routingPattern`, and `page.id`.
- Always start `routingPattern` with `/`. The hub task uses `"/"`.
- Always set `page.id` to the `.pmd` file's `id`. A task with no matching page is a broken route.
- Always set `applicationId` to the same value as `appManifest.json` `referenceId`.
- Always keep Workday base URLs in `dataProviders`, using `` <% `{{apiGatewayEndpoint}}/...` %> ``. Vehicle Registration uses `app`, `workday-common`, `workday-staffing`, `workday-wql`, and `workday-graph`.
- Always build the app data provider with `site.applicationId`. Do not paste the app id Workday generated for one tenant into a script or a URL.
- Never hardcode a `*.workday.com` host or any other tenant host inside a data provider.
- Never put `editWizard` inside `flowDefinitions`. The AMD reference forbids it.
- Use `flowDefinitions` only when the existing AMD is already a multi-step flow. `editWizard` is not a flow step.

## SMD

- Always set `id`, `siteId`, and `applicationId` to the same reference id.
- Always set `siteAuth.authTypes` to `{ "scheme": "SSO", "id": "sso" }`. Do not replace that with the doc sample's single `authType` string.
- Always map `401`, `404`, `500`, and `503` in `errorPageConfigurations` to a real error page id.
- Always list every `languages[].code` that has a file in `presentation/presentationLabels/`. Vehicle Registration ships `de-DE`, `en-US`, `es-ES`, `fr-FR`, and `ja-JP`.
- Never add sidebar `navigation` unless the existing SMD already has it.

## Manifest

- Always keep `appManifest.json` to `referenceId` and `name`, matching the AMD `applicationId`.
- Never put OAuth client secrets in the manifest. Declare scopes only when the app calls external APIs, as `requiredScopes` on the manifest, and store the secret in the tenant secret store.

## Attributes

- Put tenant-editable settings in `attributes/` with `tenantEditable: true`. Never bake a threshold or notification address into a page.

Open next: `catalog/vehicleRegistration/presentation/vehicleRegistration.amd`
