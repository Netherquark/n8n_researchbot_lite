# n8n_researchbot_lite

ResearchBot Lite is a browser-accessible research brief generator implemented as an n8n
workflow. A user submits a public research question through a form. The workflow validates
the topic, requests up to five results from Tavily, normalizes source titles, URLs, publication
metadata, and excerpts, and sends the bounded evidence set to Google Gemini 3.5 Flash-Lite.
The model is prompted to return a JSON object containing a title, executive summary, findings,
source identifiers, confidence labels, caveats, and conclusion. JavaScript Code nodes validate
the response structure, check citation identifiers against the retrieved source set, escape
dynamic HTML, and assemble the report. IF nodes route invalid input and empty evidence,
while dedicated error builders handle search and synthesis failures. The workflow contains
thirteen principal blocks and integrates n8n, Tavily Search API, and the Gemini Developer
API.
