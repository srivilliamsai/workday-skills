# Extend security

- Always give every page a `securityDomains` entry. A page with no security domain is incomplete.
- Always create a `.securitydomain` whose `name` is the same string used in the business object's `defaultSecurityDomains` and the page's `securityDomains`. Vehicle Registration uses `ManageVehicles` in all three places.
- Always set `enabledForPageSecurity: true` when pages check that domain.
- Always give the domain a `label` in the form `Manage: <object>`.
- Never let an Extend page read or write a core HCM or Financials object the signed-in user cannot see. Row security is enforced. `secureByTarget: true` on a `WORKER` field keeps that enforcement.
- Never grant a domain in the page and forget it on the business object, or the reverse.
- Gate a widget the user must not see with `<% user.hasPermission('Domain_Name') %>`. Do not hide the field by omitting the security domain.
- Map the domain to security groups in the tenant after install. App Hub Administrators deploy. App Hub Developers edit and deploy to sandbox. App Hub Auditors are read-only.
- Confirm the tenant has Workday Cloud Platform and the WCP API Gateway enabled before the first deploy.
- Never put an API key, password, or raw token in an AMD, SMD, or business object. Reference the Workday Secure Secret Store.

External callers use OAuth 2.0 client credentials or JWT bearer, scoped to the app. That is not a substitute for the page security domain.

Open next: `catalog/vehicleRegistration/model/ManageVehicles.securitydomain`
