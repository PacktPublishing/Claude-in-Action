# Review checklist

Use this for every run, on the sample pack and on your own documents.

1. Open the Exceptions sheet and the review folder side by side.
2. For each flagged row, open the source PDF and check the values against the page.
3. If the extraction is wrong, tell Claude the correction in plain language and ask it to record that you reviewed the row.
4. If the document itself is wrong, contact the vendor. Leave the extracted data as it is, since it records what the document says.
5. If the row is a false alarm, tell Claude to mark it reviewed, with a note saying why.
6. When the list is done, ask Claude to rebuild the workbook.

Before anyone schedules a payment:

- Rows across Invoices and Contracts equal the PDFs in incoming.
- Every source_file value is unique.
- The invoice total matches your accounting system.
- Every exception row has a reviewer and a decision.
- A new vendor's first invoice has been checked by a person, even if no rule flagged it.
- Nobody typed over a cell in the workbook.
