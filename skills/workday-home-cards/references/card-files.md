# Home card files

Employee Recognition is the Home card. Work From Almost Anywhere shows the same shape plus a tenant setting.

- Always store the Home card in `cards/<name>.carddefinition` at the app root.
- Always set a stable id. Employee Recognition uses `"id": "createRecognitionCard"`. A page `cardContainer` references that id as `cardId`.
- Always use `presentation.type` of `inlineCard` with `header.type` `cardHeader` (`title`, `subtitle`, `icon`) and `body.type` `simpleCard`.
- Always keep the icon on a file the app already ships, such as `WorkdayWThumbnail.jpeg`. Do not invent an icon name.
- Always add a footer action with `taskReference.taskId` set to an AMD task id when the card launches a page.
- Always add a `.cardtenantsetting` beside the card definition when the card is launched from Home: `name`, `label`, `securityDomains`, and `routePath`. Security domain names must already exist on the app. `routePath` starts with `/`. Work From Almost Anywhere ships `CreateRequestCard.cardtenantsetting`.
- Always place the card in Workday Home settings after deploy. A card file on disk does not appear on Home by itself.
- Never put the Home card layout only in a `.pmd` and skip the `.carddefinition`.
- Never hardcode a tenant host or a secret in the card.

In-app cards that are not on Home live in `presentation/cards/*.card` and are pulled into a page with `cardContainer`. Copy `catalog/pmdWidgetDictionary/presentation/cards/` for those tags.

Open next: `catalog/employeeRecognition/cards/createRecognitionCard.carddefinition`
