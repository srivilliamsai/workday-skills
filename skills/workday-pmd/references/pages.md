# PMD pages

Match Vehicle Registration `presentation/home.pmd` for endpoints and labels. Match the widget dictionary for layout tags.

- Always set `id` to the AMD task's `page.id`.
- Always set `securityDomains` to the same domain name as the business object's `defaultSecurityDomains`.
- Always give every widget an `id`.
- Always put data calls in `endPoints`, not inside widget values.
- Always set `baseUrlType` to a key declared in the AMD `dataProviders` (`workday-graph`, `workday-wql`, `app`, or another key that already exists).
- Always call Graph with `httpMethod: "POST"` and `graphQuery.queryId` set to the `.graphquery` file's `id`.
- Always set `authType` to `"sso"` on Workday endpoints. Vehicle Registration uses `"sso"` on almost every endpoint. `"SSO"` in `home.pmd` and `viewLocations.pmd` is the inconsistent form. Fix new and edited endpoints to `"sso"`.
- Always list `failOnStatusCodes` for at least `400` and `403` on every endpoint.
- Always bind with `<% ... %>`. Endpoint output is `<% endpointName.data... %>`.
- Always put user-facing copy in `<% presentationLabels.KeyName %>` and in `presentation/presentationLabels/<locale>.properties`. Never hardcode a sentence in `label` or `value` when the app already has a properties bundle.
- Always add a properties key to every locale the SMD lists. Vehicle Registration uses `de-DE`, `en-US`, `es-ES`, `fr-FR`, and `ja-JP`.
- Never leave a `console.*` call in a page or a binding. Delete it.
- Never use `authType: "noAuth"` on a Workday data provider. `noAuth` is only for the public external API the page already calls.
- Never invent an endpoint name that the presentation does not reference, or reference an endpoint that is not declared.
- Never write a `*.workday.com` host in a page.

A page body is `presentation.title` (`type: "title"`), `presentation.body` (`type: "section"`), and an optional `presentation.footer`.

Mobile uses `responsiveContainer` and `fluidGrid`. Camera capture is `fileUpload` with `capture="camera"`. Deep links use `workday://app/<appId>/<page>?id=<id>`.

Open next: `catalog/vehicleRegistration/presentation/home.pmd`
