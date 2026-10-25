---
name: document-extractor
description: Extracts fields from the invoice and contract PDFs in the incoming folder, consolidates them into output/consolidated.xlsx, flags exceptions for human review, copies flagged documents into review, and stops for the reviewer. Use when the user says "run the document-extractor skill" with a reference date, "process this month's documents", or asks to extract and consolidate invoices or contracts.
---

# Document extractor

Process every PDF in `incoming`, build one workbook in `output`, flag anything suspicious, then stop and wait for the reviewer.

## Folders

- `incoming/` holds the original PDFs. Read-only. Never change, rename, or move these files.
- `output/` holds `consolidated.xlsx`.
- `review/` holds copies of flagged documents.

## Ground rules

- Extract only what is printed in a document. Never infer or calculate a value that is not on the page.
- If a value is unreadable, write UNREADABLE and rate that document's confidence as low.
- Rate every document's confidence as high, medium, or low.

## Reference date

Rules 4 and 6 count from the reference date in the user's run instruction. If the instruction gives none, ask for it before starting. Never use the system date.

## Step 1: count

List the files in `incoming` and report how many PDFs there are.

## Step 2: extract

Go through the PDFs one at a time. Identify whether each is an invoice or a contract, then apply the matching rules.

Invoice rules:

- Vendor name: legal name as printed
- Invoice number: exactly as printed
- Invoice date and due date: YYYY-MM-DD
- Currency: three-letter code (USD, EUR, RON)
- Subtotal, tax, total: plain numbers, no currency symbol; use 0 for tax if it is not itemized
- Treat "Amount Payable", "Total Due", "Balance Due", and "Total amount" as the total field
- PO number: write NONE if absent

Contract rules:

- Counterparty name and contract title, as printed
- Effective date and end date: YYYY-MM-DD; write EVERGREEN if there is no end date
- Contract value per year: plain number; write VARIABLE if pricing is usage-based
- Currency: three-letter code
- Renewal type: AUTO, MANUAL, or NONE
- Notice period in days: write NOT_STATED if absent

Report: documents found, documents extracted, and any document with an unreadable value or low confidence.

## Step 3: build the workbook

Build `output/consolidated.xlsx` with three sheets.

- Invoices: vendor_name, invoice_number, invoice_date, due_date, currency, subtotal, tax, total, po_number, confidence, source_file
- Contracts: counterparty, contract_title, effective_date, end_date, annual_value, currency, renewal_type, notice_period_days, confidence, source_file
- Exceptions: source_file, rule, detail

One row per document. Bold header rows, freeze the top row, and format amount columns as numbers with two decimals. Build the file from the extracted data; never type values into cells by hand.

Verify, then report: rows across Invoices and Contracts equal the number of PDFs in `incoming`, every source_file value is unique, and the sum of the Total column on Invoices.

## Step 4: flag exceptions

Flag any row where:

1. A field is missing or UNREADABLE
2. Subtotal plus tax differs from the total by more than 0.01
3. An invoice number repeats for the same vendor
4. A due date comes before the invoice date, or any date falls more than 3 years before or 10 years after the reference date
5. Confidence is low
6. A contract renews automatically and its notice window closes within 60 days after the reference date

Flagged rows stay on their normal sheet and also get a row on Exceptions: source_file, the rule number, and a detail line showing the suspect values. Copy each flagged document from `incoming` into `review`. Rebuild the workbook.

Report how many rows were flagged, by rule.

## Step 5: stop for review

Stop here. Do not approve, correct, or dismiss any flagged row on your own.

When the reviewer gives a decision in plain language, update the extracted data, record the decision and the reviewer's name against that row, and rebuild the workbook. Never edit a cell directly.
