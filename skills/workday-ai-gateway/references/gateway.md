# AI Gateway

- Always call the Gateway from an orchestration or an Extend endpoint, inside the Workday boundary. Do not send worker documents from the browser to a public model.
- Always pick the capability the Workday catalog already ships: document intelligence for OCR and key-value extraction, WQL generation for a natural-language query, or sentiment analysis on text the app already stores.
- Always follow the Gateway call shape in `catalog/documentIntelligenceWithTheAIGateway` or `catalog/generateWQL`. Do not invent a Gateway path.
- Always treat Gateway output as untrusted until the page or flow validates required fields. A missing invoice total is a validation error, not a zero.
- Never send customer data to a model training job. Gateway requests are not retained for public model training.
- Never put a document image or a model response in a log line.
- Never invent a Gateway path that is not in the sample you opened.

Sentiment and anomaly scores are Intelligent Services outputs. Show them as scores. Do not turn a score into an automatic deny unless the sample flow already does that.

Open next: `catalog/documentIntelligenceWithTheAIGateway`
