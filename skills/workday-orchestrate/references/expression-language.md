# Orchestrate expression language

- Always use single quotes for string literals inside an expression so the surrounding JSON does not need extra escaping.
- Always use `?.` before a field that may be missing.
- Always use `??` for a fallback: `user.nickname ?? user.firstName`.
- Always split a multi-step calculation across sequential map steps. Do not nest a long expression in one property.
- Always use `jsonpath(body, '$.path')` for JSON and `xpath(body, '//node/text()')` for XML. Do not hand-parse either.
- Never use a deep scan (`..` or `//`) on a document larger than 5MB inside a loop.
- Never call a function that is not in the global or member function reference. Open those docs before adding a call.

Global functions from the reference:

- `date:now()`
- `date:format(dateTime, pattern)`
- `str:concat(...)`
- `str:trim(str)`
- `num:round(decimal, scale)`
- `uuid:random()`

PMD scripts use the same `date:` prefix. Orchestrate expressions are not JavaScript. Do not paste a PMD `function` into a flow.

Open next: `Documentation/Integration Apps/Orchestrate Expression Language/Global Functions Reference.md`
