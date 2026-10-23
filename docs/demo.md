# Portfolio Demo Script

## Demo 1 — Retrieve sales data

Ask: "Using your Knowledge sources, list each product and its revenue from the sample sales dataset."

Verify that the response cites the uploaded source and matches `data/sales_data.csv`.

## Demo 2 — Run an external calculator

Ask: "Use your calculator tool to calculate 23 × 19 and show the tool result."

Expected result: `437`. Check that **the tool actually ran** in the activity trace.

## Demo 3 — Generate a report

Ask: "Use the Sales Report Generator to analyze the sample sales data. Include KPIs, revenue percentages, and recommendations."

Expected KPIs: ₹441,000 revenue, 58 units, Laptop contribution about 56.69%.

## Demo 4 — Deliver an approved report to Make

Generate and review the report first; then explicitly approve creating **one Gmail draft**. Verify the HTTP tool execution, webhook payload, and created Gmail draft. Never show the webhook URL or private email addresses during recording.

## Resume/project description

"Built a no-code AI sales reporting workflow using Botpress Viber, RAG-based PDF retrieval, Math.js tool calling, and Make.com automation. Generated KPI reports and implemented approval-controlled Gmail draft creation using webhooks and dynamic JSON mapping."
