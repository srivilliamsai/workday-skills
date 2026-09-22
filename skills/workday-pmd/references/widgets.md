# PMD widgets

Copy the tag from `catalog/pmdWidgetDictionary/presentation/`. The dictionary page name is the widget.

- Always wrap fields in `section`. Use `fieldSet` inside a section when the dictionary page does.
- Always set `gridType`, `rowVariableName`, `columns`, and a stable `id` on a `grid`. Vehicle Registration uses `gridType: "LIST"`.
- Always set both `id` and `columnId` on a column, and render the cell with `cellTemplate`.
- Always navigate with `taskReference.taskId` set to an AMD task id, and pass ids in `parameterBindings`. Do not build a raw URL.
- Always set `doNotAdd` and `doNotRemove` on a grid the user must not edit.
- Always use the dictionary types for inputs: `text`, `textArea`, `dropdown`, `date`, `checkBox`, `radioGroup`, `richText`, `button`.
- Always include a shared card with `cardContainer` and `cards[].cardId` matching the `.card` id. Card file rules live in `workday-home-cards`.
- Prefer boolean `false` for `enabled` when the rest of the page uses booleans. Do not mix `false` and `"false"` on the same page. The widget dictionary sometimes uses the string `"false"`; match the file you are editing.
- Never add a widget type that has no page in the widget dictionary.
- Never put an `editWizard` inside an AMD `flowDefinitions` block. Wizard pages belong in `presentation/`, as `editWizard.pmd` does in the dictionary.

Pods are included with `"include": ["commonFooter.pod"]` when the app already has `presentation/pods/`.

Open next: `catalog/pmdWidgetDictionary/presentation/basicWidgets.pmd`
