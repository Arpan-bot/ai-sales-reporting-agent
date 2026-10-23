# Setup Guide (No Code)

> This repository documents an existing hosted workflow. You will need accounts and access to Botpress, Make, and Gmail to reproduce it. Never paste secret webhook URLs into public files.

## 1. Botpress agent

1. Create an agent in Botpress Viber.
2. Under **Build → Instructions**, define its role as a beginner-friendly data analytics assistant.
3. Under **Build → Knowledge**, add a PDF generated from the fictional dataset in `../data/sales_data.csv`.
4. Under **Build → Tools**, configure a Math.js Calculator HTTP tool:
   - Method: GET
   - Endpoint: `https://api.mathjs.org/v4/`
   - Query parameter: `expr`, supplied dynamically from a required input
5. Create a **Calculator Operations** Playbook and reference the actual calculator tool.
6. Create a **Sales Report Generator** Playbook that retrieves data, calculates KPIs, and formats the result.
7. Test both knowledge retrieval and real calculator calls in Preview.

## 2. Make scenario

1. Add **Webhooks → Custom webhook**.
2. Add **Gmail → Create a Draft Email**.
3. Configure the Gmail connection and map only the webhook `report` value into **Body contents → Content 1 → Text**.
4. Validate with fictional test text. Do not use Gmail's Send Email action for this project.
5. Protect the webhook and retain its URL privately.

## 3. Botpress delivery action

1. Create an HTTP POST tool targeting your **private** Make webhook.
2. Set `Content-Type: application/json`.
3. Provide a required dynamic `report` text input.
4. Ensure the outbound JSON body is safely serialized: a report may contain newlines, quotation marks, and other characters. Test this with a harmless multiline message.
5. Create an **Email Report Delivery** Playbook that requires explicit approval before invoking the delivery tool once.
6. Inspect both Botpress execution activity and Make's execution log to verify the actual tool call and mapped report text.

## 4. Optional Make blueprint export

In Make's scenario builder select **three dots → Export blueprint**. Before publishing the resulting JSON, check and remove webhook URLs, connection identifiers, personal information, and secrets. A Make blueprint is not the same as a functioning credentialed connection.

## 5. Verification checklist

- [ ] Knowledge search returns the sample product records
- [ ] Math.js appears as an actual tool execution in Botpress Preview
- [ ] Revenue totals match the fictional CSV
- [ ] Report content is generated in chat
- [ ] Delivery waits for explicit draft approval
- [ ] Make receives the dynamic `report` field
- [ ] Gmail draft contains the intended multiline content
- [ ] No email is sent automatically
- [ ] No webhook URLs or account details appear in public files
