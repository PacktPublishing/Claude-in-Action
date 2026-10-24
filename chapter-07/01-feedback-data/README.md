# The feedback data

## Upload the sheet

1. In Google Drive, upload `silverpine-feedback-Q2.csv`.
2. Right-click it and choose **Open with | Google Sheets**. This creates a Google Sheet next to the CSV.
3. Rename the new sheet to exactly `Silverpine Feedback Form Responses`. Every prompt in the chapter uses that name.
4. Check the timestamp column. Select column A and apply **Format | Number | Date time**, the same check the chapter describes. Depending on your Drive locale the import may read the dates as text.

You can delete the uploaded CSV once the sheet exists. Claude reads the Google Sheet through the connector, not the CSV.

## The columns

| Column | Contents |
|---|---|
| A | Timestamp |
| B | Business type |
| C | Tenure with Silverpine |
| D | Satisfaction, 1 to 5 |
| E | Most-used feature |
| F | Biggest frustration (free text) |
| G | One thing to add or change (free text) |
| H | Anything else (free text) |
| I | Consent to contact |
| J | Email, only where consent was given |

The analysis prompt reads F, G and H for themes, and B and C for context. If your own sheet puts these elsewhere, change the column letters in the prompt and the skill.

## The July batch

`silverpine-feedback-July.csv` holds 60 responses dated June 29 to July 28, 2026, with the same ten columns.

Use it only after you have an approved Q2 roadmap in your folder. To simulate a month passing, open the CSV, copy every row except the header, and paste them directly under the last row of the Google Sheet. Then run the update prompt from `02-prompts/07-update.md`. The new rows land at sheet rows 191 to 250.

## What is deliberately in the data

The sheet carries the traps the chapter describes, so you can see them happen:

- Two SMS themes that look like one: reminder caps (a plan-limits decision) and broken Romanian and Hungarian characters (an encoding bug)
- Mobile complaints phrased two ways, "the mobile page freezes" and "clients cannot book from their phones", which one fix resolves
- One customer writing about the same request in April, May and June, identifiable only by her email address
- A quote that identifies a customer without naming her: a two-person salon in the old town square
- A customer thanking the team for shipping recurring invoices, in the June data
