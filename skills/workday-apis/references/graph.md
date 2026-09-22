# Graph API

Catalog queries are `.graphquery` JSON files, not standalone GraphQL documents.

Vehicle Registration `me.graphquery`:

```json
{
  "id": "me",
  "query": "query { worker(dataSource:{ processingWorker:{}}) { data { workdayID {id} primaryJob { location { workdayID { id}}} }}}"
}
```

- Always set `id` to the `graphQuery.queryId` on the PMD endpoint.
- Always keep the query in the `query` string. Request only the fields the page reads.
- Always call it with `baseUrlType: "workday-graph"`, `httpMethod: "POST"`, and `authType: "sso"`.
- Always pass variables through `graphQuery.parameters` using `<% %>` bindings, as `home.pmd` does for `ownerId`.
- Always paginate large lists with `first` and `after`, and stop when `pageInfo.hasNextPage` is false. Read `endCursor` for the next page.
- Always check `errors` on a mutation before reading the updated object.
- Never over-fetch a worker profile when the page needs one id.
- Never put the query only in the PMD file and skip the `.graphquery` file.

Open next: `catalog/vehicleRegistration/presentation/graphQueries/me.graphquery`
