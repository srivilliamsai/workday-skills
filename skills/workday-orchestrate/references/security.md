# Orchestration security

- Always use OAuth 2.0 client credentials for a headless system-to-system call. Use authorization code only when a user delegates access.
- Always use mutual TLS when the partner requires a client certificate. Store the PKCS#12 key in Manage Integration Keystores and reference the alias from the HTTP step. Put private CA certificates in Manage Integration Truststores.
- Always require a bearer token on an inbound HTTP listener, and restrict the gateway to known CIDR blocks.
- Always create a purpose-specific Integration System Security Group. Grant only the GET or PUT operations the flow calls.
- Never grant an Integration System User administrator or broad reporting access.
- Never put a client secret, password, or certificate body in the orchestration JSON. Basic authentication is legacy only. Do not add it to a new flow.
- Never log the Authorization header or the request body when it contains pay, bank, or government id data.

Open next: `Documentation/Integration Apps/Integration App Authentication and Security/Authentication Methods.md`
