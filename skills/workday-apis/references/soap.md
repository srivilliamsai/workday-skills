# SOAP and WWS

- Always address the tenant cluster by FQDN: `https://<tenant-services-host>/ccx/service/{tenant}/{serviceName}/<version>`. Do not pin an IP.
- Always authenticate with WS-Security UsernameToken or an X.509 signature. Encrypt payroll and bank fields when the service requires XML Encryption.
- Always use a `Put_` operation for mass loads, in chunks of 500 to 1,000 records, and stay inside the rate limit across ISU sessions.
- Always take `wsdl`, `operation`, and the envelope from the sample you are copying. Worker Image Upload Inbound is the catalog SOAP inbound.
- Never build a SOAP body as a string inside a PMD page. SOAP belongs in an orchestration `SOAP_INVOKER` step.
- Never log the full envelope when it contains a photo, bank account, or national id.

Open next: `catalog/workerInboundImageUpload`
