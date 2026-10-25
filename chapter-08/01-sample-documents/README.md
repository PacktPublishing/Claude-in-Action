# Sample documents

## Month 1: June 2026 (15 PDFs)

12 invoices and 3 contracts from Cedarline's vendors. Put all 15 in your `incoming` folder at step 4 of the setup.

The invoices come in four layouts on purpose. One puts the total in a box at the top right, one uses European number and date formats (3.996,00 USD, 15.06.2026), one is a law firm's statement of account, and the rest put the totals below the line items. Dates appear as June 3, 2026, 06/15/2026, 15.06.2026, and 11 Jun 2026. Your extraction rules turn all of them into the same columns.

Three documents are built to trip the exception rules. Do not open the answer key until you have run the exception step yourself.

## Month 2: July 2026 (12 PDFs)

10 invoices and 2 contracts. Use them only at the end of the chapter, after you have packaged the skill. Empty `incoming` first, then copy these in and send `Run the document-extractor skill with 2026-08-05 as the reference date.`

This batch includes a vendor Cedarline has never paid before, a document that labels its total "Amount Payable", and problems the June batch did not have.

## About the dates

Rules 4 and 6 count from a fixed reference date that you give Claude, so these documents produce the same flags whenever you run them. Use 2026-07-06 for the June batch, as in the exception rules prompt, and 2026-08-05 for the July batch, as in the skill run prompt. On your own documents, use the date of the run.
