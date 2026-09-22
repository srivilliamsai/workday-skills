# PMD scripting

Match `catalog/pmdScripting`.

- Always put scripts in `presentation/scripts/<name>.script`.
- Always end the script with an export object that names every function the page calls:

```javascript
{
  "logData": logData
}
```

- Always include the script from the page with `"include": ["<name>.script"]` before using it.
- Always call namespaced helpers the way the script sample does: `date:getTodaysDate`, `date:getDateTimeZone`. Do not invent `new Date()` for a value the page displays.
- Always log with `console.debug`, `console.info`, `console.warn`, or `console.error`. Those lines show in Developer Site Analytics when the filter is `wd_category is console`.
- Never call `console.*` inside a widget `value` or `rows` binding. Call a script function, or delete the log.
- Never export a function the page does not include, and never call a function that is not in the export object.

Open the script pair next to the page: `logging.script` with `logging.pmd`, `gridEvents.script` with `gridEvents.pmd`, `invokingEndpoints.script` with `invokingEndpoints.pmd`.

Open next: `catalog/pmdScripting/presentation/scripts/logging.script`
