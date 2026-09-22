# Orchestration operations

## Retry and polling

On outbound HTTP and SOAP steps:

- Retry `429`, `500`, `502`, `503`, and `504`.
- Cap retries at 3, start at 2 seconds, backoff factor 2, max interval 30 seconds.
- Do not retry `400` or `401`. Fix the payload or the token.
- Poll a long job with an interval, a max duration, a completion condition, and a failure condition. Do not poll forever.

Wrap the outbound call in try/catch. On `HTTP_CLIENT_ERROR`, write an audit log and route the payload to a dead-letter queue. Release connections in `finally`.

## Deploy

Commit, build in App Hub, pass schema and unit checks, then promote the immutable package. Do not edit a flow in production.

## When a run fails

1. Read the integration event. Treat `Failed` and `Completed With Warnings` as different outcomes.
2. Read the `error` object on the failing step.
3. Export the step trace.
4. Replay the payload with mock data in a sandbox.

Open next: `Documentation/Integration Apps/Integration App Development/HTTP Retry and Polling Policies.md`
