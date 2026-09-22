# WQL

Match `employeeSearch.wqlquery`:

```json
{
  "id": "employeeSearch",
  "parameters": ["manager"],
  "query": "SELECT fullLegalName AS descriptor, workdayID AS id FROM workersForHCMReporting (dataSourceFilter = allActiveWorkers) WHERE (activeStatus = true AND manager_Level01 in (<% manager %>))"
}
```

- Always store the query in `presentation/wqlQueries/<id>.wqlquery` with `id`, `parameters`, and `query`.
- Always list every `<% name %>` token in `parameters`.
- Always name a data source. Reporting queries use `workersForHCMReporting (dataSourceFilter = allActiveWorkers)`. The short doc sample `FROM allActiveWorkers` is the language form. Prefer the data source the sample file already uses.
- Always filter in `WHERE`. Aggregate with `COUNT` and `AVG`, then `GROUP BY` and `HAVING`. Do not filter a huge result in the page.
- Always call WQL through the `workday-wql` data provider or `POST` to the WQL data endpoint with a bearer token. Do not embed the token.
- Custom objects use their qualified name from the business object. Do not guess the namespace.
- Never interpolate a raw user string into the query without a declared parameter.

Open next: `catalog/employeeRecognition/presentation/wqlQueries/employeeSearch.wqlquery`
