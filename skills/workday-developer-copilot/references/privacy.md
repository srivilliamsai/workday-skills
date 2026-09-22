# Workday Developer Copilot privacy

- Never paste a client secret, access token, refresh token, certificate, or webhook URL.
- Never paste production worker rows, pay, bank data, government ids, or résumés.
- Never paste a tenant hostname that identifies a customer production tenant. Say "sandbox tenant" instead.
- Prompts stay inside the signed-in developer's tenant. They are not used to train a public model. Do not assume that means the prompt is a safe place for secrets.
- Copilot runs only where an administrator has opted the tenant in. If it is off, do not try to route around that setting.

Use fictional names in example payloads, the way the API prompt doc uses `alex.morgan@example.com`.

Open next: `Documentation/Workday Developer Copilot/Workday Developer Copilot Overview/Security and Data Privacy.md`
