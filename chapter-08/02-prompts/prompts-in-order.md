# Prompts in order

Every prompt from Chapter 8, in the order you send it. Copy each block as it is. Lines marked optional are only needed in the situation described.

## Setting up the workspace

Before the first prompt, open the Claude app and go to </> | New (</> is the Code icon). Set the environment to This computer, point the folder at a new folder named `Cedarline Property Management`, and choose Trust Workspace.

**1. Create the folders**

```
Create three empty folders named incoming, output, and review.
```

Copy the 15 PDFs from `01-sample-documents/month-1-june` into `incoming`.

**2. Count the files**

```
List the files in incoming and tell me how many PDFs there are.
```

Claude should report 15.

## Defining the fields

**3. Invoice rules**

```
Here are the extraction rules for invoices. Learn them;
we will use them for every document in this project.
- Vendor name: legal name as printed
- Invoice number: exactly as printed
- Invoice date and due date: format as YYYY-MM-DD
- Currency: three-letter code (USD, EUR, RON)
- Subtotal, tax, total: plain numbers, no currency symbol;
 use 0 for tax if it is not itemized
- PO number: write NONE if absent
```

**4. Contract rules**

```
Extraction rules for contracts:
- Counterparty name and contract title, as printed
- Effective date and end date: YYYY-MM-DD; write
 EVERGREEN if there is no end date
- Contract value per year: plain number; write VARIABLE
 if pricing is usage-based
- Currency: three-letter code
- Renewal type: AUTO, MANUAL, or NONE
- Notice period in days: write NOT_STATED if absent
```

**5. Ground rules**

```
Ground rules for this whole project:
- Files in incoming are read-only. Never change them.
- Extract only what is printed in a document. Never infer
 or calculate a value that is not on the page.
- If a value is unreadable, write UNREADABLE and rate
 that document's confidence as low. Rate every document's
 confidence as high, medium, or low.
```

## Processing documents in bulk

**6. Run the extraction**

```
Go through every PDF in incoming, one document at a time.
Identify whether each is an invoice or a contract, and
extract the fields using the rules you learned. Keep the
results in a working table with one row per document,
including the source filename and the confidence rating.
When you finish, report: documents found, documents
extracted, and any document with an unreadable value or
low confidence.
```

**7. Check one record against its PDF**

```
Show me every extracted field and its value for the Kestrel HVAC invoice.
```

Repeat for three or four documents, including at least one contract.

**8. Rerun after changing a rule (optional)**

```
Redo the extraction for all of incoming with the updated rules.
```

## Consolidating into Excel

**9. Build the workbook**

```
Build output/consolidated.xlsx with three sheets: Invoices,
Contracts, and Exceptions. One row per document, with a
source_file column at the end of every row. Make header
rows bold, freeze the top row, and format amount columns
as numbers with two decimals. Leave Exceptions empty for
now. When done, report the row count per sheet.
```

**10. See how it was built (optional)**

```
Explain how you built the workbook, in plain language
```

**11. Verify the workbook**

```
Verify consolidated.xlsx: confirm the number of rows across
all sheets equals the number of PDFs in incoming, confirm
every source_file value is unique, and give me the sum of
the Total column on the Invoices sheet.
```

## Flagging exceptions

**12. Exception rules**

```
Exception rules. Use 2026-07-06 as the reference date.
Flag any row where:
1. A field is missing or UNREADABLE
2. Subtotal plus tax differs from the total by more
 than 0.01
3. An invoice number repeats for the same vendor
4. A due date comes before the invoice date, or any date
 falls more than 3 years before or 10 years after the
 reference date
5. Confidence is low
6. A contract renews automatically and its notice window
 closes within 60 days after the reference date
Do not apply these yet. Confirm you have all six, and wait for my next instruction.
```

**13. Apply the rules**

```
Apply the exception rules to every extracted row. Flagged
rows stay on their normal sheet and also get a row on the
Exceptions sheet with: source_file, the rule number, and a
detail line showing the suspect values. Copy each flagged
document from incoming into review. Rebuild the workbook
and report how many rows were flagged, by rule.
```

**14. Record a review decision (example)**

```
The tax on invoice CRS-1188 reads 168.00 as extracted; the vendor's total is the error. Keep our values, note the invoice as disputed, and record that I reviewed this row.
```

Handle the other flagged rows the same way, in your own words. When the list is done, ask Claude to rebuild the workbook.

## Packing the workflow into a skill

**15. Package the skill**

```
Package this whole workflow into a skill called
document-extractor: the three-folder layout, the invoice
and contract extraction rules, the ground rules, the
workbook format, the exception rules, and the reports you
give me at each stage. Take the reference date from my
run instruction. Running the skill should process
whatever is in incoming, end to end, and stop for my
review after the exceptions report.
```

**16. Run it on the July batch**

Empty `incoming`, copy in the 12 PDFs from `01-sample-documents/month-2-july`, then send:

```
Run the document-extractor skill with 2026-08-05 as the reference date.
```

**17. Refine the skill (example)**

```
Update the document-extractor skill: treat "Amount Payable" as the total field.
```
