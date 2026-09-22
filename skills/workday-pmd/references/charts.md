# PMD charts

Match Chart Dictionary pages such as `comboChart2.pmd`. Read the page for the chart you need. Do not invent chart property names.

- Always set the widget `type` to the chart tag from that page (`comboChart2` and the other `*Chart2` files in `presentation/`).
- Always load the data script with `include`, then set `data` to the script function and `dataVariableName` to the row name used in each `value`.
- Always put series in `measurementDataSets` with `name`, `value`, and `chartMarkType` (`BAR`, `LINE`, or `POINT` as that page already uses).
- Always set `legendPosition` from the sample (`BOTTOM` on the combo chart) instead of a new enum value.
- Never draw a chart with hand-built `grid` cells when a Chart Dictionary page already shows the chart type.
- Never point `data` at an endpoint body unless that chart page does. The combo chart reads a script function.

Open next: `catalog/chartDictionary/presentation/comboChart2.pmd`
