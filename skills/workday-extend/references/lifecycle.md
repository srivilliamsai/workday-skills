# Extend lifecycle

## Local commands

- `wdcli auth:login` before the first call.
- `wdcli app:create` to scaffold. `wdcli app:pull --app-id <id>` to clone.
- `wdcli app:validate` before push. `wdcli app:watch` while editing. `wdcli app:push` to the development tenant.
- `wdcli app:build` then `wdcli app:deploy` for a package. `wdcli logs:tail` for runtime logs.

## Versions

App Hub uses `major.minor.patch`.

- Patch: cosmetic or non-breaking metadata.
- Minor: new page or optional field.
- Major: breaking schema or a changed route.

A build checks PMD and SMD schema, model dependencies, and route resolution. Do not promote a build that fails those checks.

## Promotion

1. Lock the release candidate in App Hub.
2. Generate the App Release Package.
3. Sign in to the target tenant as an App Hub Administrator.
4. Run Install or Update Extend Application.
5. Map security domains and set tenant attributes.

## Retirement

Deactivate public routes, archive business object data, mark the app Deprecated in App Hub, and delete it only after the audit window. Do not delete the object while reports still read it.

Built-on-Workday apps externalize every user-facing string and contain no tenant host and no credential.

Open next: `catalog/tuitionReimbursement`
