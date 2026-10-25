# Sample outputs

What the workbook should look like at three points in the chapter. Your column widths and some wording in the detail lines will differ. The values should not.

- `consolidated-june-after-exceptions.xlsx` is the June batch after prompt 13: 12 invoices, 3 contracts, and 4 exception rows covering 3 documents.
- `consolidated-june-reviewed.xlsx` is the same workbook after a review pass. The Exceptions sheet gains status, reviewed_by, and review_note columns. The reviewer read the Halvorsen tax from the paper original and gave it to Claude, so the Invoices sheet now shows 69.20 where it said UNREADABLE.
- `consolidated-july.xlsx` is the July batch after `Run the document-extractor skill with 2026-08-05 as the reference date.`
- `run-log.md` is an example of the one-line record the chapter suggests keeping after each run.
