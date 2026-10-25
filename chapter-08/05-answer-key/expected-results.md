# Expected results

Values as Claude should extract them with the rules from the chapter. The exceptions use the reference dates from the prompts: 2026-07-06 for June and 2026-08-05 for July.

## What each tricky document tests

**June**

- `2026-06_kestrel-hvac_invoice.pdf` is the record the chapter checks field by field. Total in a box at the top right.
- `2026-06_corran-roofing_invoice.pdf` states a total of 2286.00. Subtotal 2100.00 plus tax 168.00 is 2268.00, so rule 2 fires. Claude must extract 2286.00 as printed and must not correct it.
- `2026-06_halvorsen-plumbing_invoice.pdf` is a crooked, image-only scan with the tax line blurred. Expect tax UNREADABLE, confidence low, and rules 1 and 5. Claude may also mention that rule 2 cannot be checked on this row, which is fine.
- `2025-10_dunmore-cleaning_contract.pdf` renews automatically on 2026-09-30, and clause 9.2 sets a 60-day notice period. The notice window closes on 2026-08-01, 26 days after the reference date, so rule 6 fires.
- `2026-06_dunmore-cleaning_invoice.pdf` uses European formats. 3.996,00 USD must become 3996.00, and 15.06.2026 must become 2026-06-15.
- `2026-06_pryce-latham_invoice.pdf` and `2026-06_northgate-elevator_invoice.pdf` itemize no tax, so tax is 0, and their totals are labeled Total Due and Balance Due.
- `2025-03_pryce-latham_contract.pdf` exercises three missing-value markers at once: EVERGREEN, VARIABLE, and NOT_STATED.

**July**

- `2026-07_ridgeway-waste_invoice.pdf` and `2026-07_ridgeway-waste_invoice-resent.pdf` carry the same invoice number. Rule 3 flags both rows. Paying both would pay the vendor twice.
- `2026-07_ashby-pest_invoice.pdf` has a due date 18 days before its invoice date. Rule 4 fires.
- `2026-07_pryce-latham_invoice.pdf` labels its total "Amount Payable" and uses no other total label. If the skill misses it, this is the gap prompt 17 closes.
- `2026-07_fairmont-glass_invoice.pdf` is from a vendor Cedarline has never paid. No rule flags it, and the chapter says to route a new vendor's first invoice through review anyway. Decide that one yourself.
- `2025-11_ridgeway-waste_contract.pdf` renews automatically on 2026-10-31 with 45 days' notice. The window closes on 2026-09-16, 42 days after the reference date, so rule 6 fires.

## What can differ without being wrong

- Wording of the detail lines on the Exceptions sheet.
- Column names, if you did not specify them. The values must match.
- Order of rows.
- Whether Claude writes the notice period as 60 or "60".

Anything else that differs is worth checking against the PDF.

### June (month 1): Invoices

| vendor_name | invoice_number | invoice_date | due_date | currency | subtotal | tax | total | po_number | confidence | source_file |
|---|---|---|---|---|---|---|---|---|---|---|
| Kestrel HVAC Services LLC | KHV-2214 | 2026-06-03 | 2026-07-03 | USD | 1840.00 | 147.20 | 1987.20 | CED-0977 | high | 2026-06_kestrel-hvac_invoice.pdf |
| Corran Roofing Supply Inc. | CRS-1188 | 2026-06-15 | 2026-07-15 | USD | 2100.00 | 168.00 | 2286.00 | CED-0981 | high | 2026-06_corran-roofing_invoice.pdf |
| Dunmore Cleaning Co. | DCC-26-0615 | 2026-06-15 | 2026-07-15 | USD | 3700.00 | 296.00 | 3996.00 | NONE | high | 2026-06_dunmore-cleaning_invoice.pdf |
| Pryce & Latham LLP | PL-INV-40217 | 2026-06-30 | 2026-07-30 | USD | 6083.50 | 0.00 | 6083.50 | NONE | high | 2026-06_pryce-latham_invoice.pdf |
| Halvorsen Plumbing & Sewer Inc. | HPS-3071 | 2026-06-11 | 2026-06-25 | USD | 865.00 | UNREADABLE | 934.20 | CED-0979 | low | 2026-06_halvorsen-plumbing_invoice.pdf |
| Bramwell Electric Company | BE-55102 | 2026-06-18 | 2026-07-18 | USD | 1265.00 | 101.20 | 1366.20 | CED-0984 | high | 2026-06_bramwell-electric_invoice.pdf |
| Greenhollow Landscaping LLC | GHL-0419 | 2026-06-26 | 2026-07-26 | USD | 2480.00 | 198.40 | 2678.40 | CED-0988 | high | 2026-06_greenhollow-landscaping_invoice.pdf |
| Northgate Elevator Services Inc. | NES-77031 | 2026-06-01 | 2026-07-01 | USD | 1950.00 | 156.00 | 2106.00 | NONE | high | 2026-06_northgate-elevator_invoice.pdf |
| Ashby Pest Control | APC-2290 | 2026-06-20 | 2026-07-20 | USD | 420.00 | 33.60 | 453.60 | NONE | high | 2026-06_ashby-pest_invoice.pdf |
| Tallis Locksmiths | TL-1043 | 2026-06-09 | 2026-06-23 | USD | 312.50 | 25.00 | 337.50 | NONE | high | 2026-06_tallis-locksmiths_invoice.pdf |
| Ridgeway Waste Services Inc. | RWS-660218 | 2026-06-30 | 2026-07-30 | USD | 1180.00 | 94.40 | 1274.40 | CED-0990 | high | 2026-06_ridgeway-waste_invoice.pdf |
| Copperline Paint & Supply | CPS-8812 | 2026-06-24 | 2026-07-24 | USD | 755.00 | 60.40 | 815.40 | CED-0986 | high | 2026-06_copperline-paint_invoice.pdf |

### June (month 1): Contracts

| counterparty | contract_title | effective_date | end_date | annual_value | currency | renewal_type | notice_period_days | confidence | source_file |
|---|---|---|---|---|---|---|---|---|---|
| Dunmore Cleaning Co. | Janitorial Services Agreement | 2025-10-01 | 2026-09-30 | 44400.00 | USD | AUTO | 60 | high | 2025-10_dunmore-cleaning_contract.pdf |
| Kestrel HVAC Services LLC | Preventive Maintenance Agreement | 2026-01-01 | 2027-12-31 | 6000.00 | USD | MANUAL | 90 | high | 2026-01_kestrel-hvac_contract.pdf |
| Pryce & Latham LLP | Engagement Letter for Legal Services | 2025-03-01 | EVERGREEN | VARIABLE | USD | NONE | NOT_STATED | high | 2025-03_pryce-latham_contract.pdf |

### June (month 1): Exceptions

| source_file | rule | detail |
|---|---|---|
| 2026-06_corran-roofing_invoice.pdf | 2 | subtotal 2100.00 + tax 168.00 = 2268.00, document states 2286.00 |
| 2026-06_halvorsen-plumbing_invoice.pdf | 1 | tax is UNREADABLE |
| 2026-06_halvorsen-plumbing_invoice.pdf | 5 | confidence is low (scanned page, tax line blurred) |
| 2025-10_dunmore-cleaning_contract.pdf | 6 | renews automatically; end date 2026-09-30, notice 60 days, notice window closes 2026-08-01 (26 days after the reference date) |

### June (month 1): verification numbers

- PDFs in incoming: 15
- Rows across Invoices and Contracts: 15
- Sum of the Total column on Invoices: 24,318.40 USD
- Documents flagged: 3, exception rows: 4

### July (month 2): Invoices

| vendor_name | invoice_number | invoice_date | due_date | currency | subtotal | tax | total | po_number | confidence | source_file |
|---|---|---|---|---|---|---|---|---|---|---|
| Kestrel HVAC Services LLC | KHV-2251 | 2026-07-08 | 2026-08-07 | USD | 1500.00 | 120.00 | 1620.00 | CED-1012 | high | 2026-07_kestrel-hvac_invoice.pdf |
| Dunmore Cleaning Co. | DCC-26-0714 | 2026-07-14 | 2026-08-13 | USD | 3700.00 | 296.00 | 3996.00 | NONE | high | 2026-07_dunmore-cleaning_invoice.pdf |
| Corran Roofing Supply Inc. | CRS-1203 | 2026-07-16 | 2026-08-15 | USD | 540.00 | 43.20 | 583.20 | CED-1019 | high | 2026-07_corran-roofing_invoice.pdf |
| Pryce & Latham LLP | PL-INV-40288 | 2026-07-31 | 2026-08-30 | USD | 4304.80 | 0.00 | 4304.80 | NONE | high | 2026-07_pryce-latham_invoice.pdf |
| Ridgeway Waste Services Inc. | RWS-660291 | 2026-07-31 | 2026-08-30 | USD | 980.00 | 78.40 | 1058.40 | CED-1024 | high | 2026-07_ridgeway-waste_invoice.pdf |
| Ridgeway Waste Services Inc. | RWS-660291 | 2026-07-31 | 2026-08-30 | USD | 980.00 | 78.40 | 1058.40 | CED-1024 | high | 2026-07_ridgeway-waste_invoice-resent.pdf |
| Ashby Pest Control | APC-2318 | 2026-07-20 | 2026-07-02 | USD | 420.00 | 33.60 | 453.60 | NONE | high | 2026-07_ashby-pest_invoice.pdf |
| Greenhollow Landscaping LLC | GHL-0447 | 2026-07-28 | 2026-08-27 | USD | 1860.00 | 148.80 | 2008.80 | CED-1027 | high | 2026-07_greenhollow-landscaping_invoice.pdf |
| Bramwell Electric Company | BE-55167 | 2026-07-22 | 2026-08-21 | USD | 570.00 | 45.60 | 615.60 | CED-1021 | high | 2026-07_bramwell-electric_invoice.pdf |
| Fairmont Glass & Glazing LLC | FGG-1007 | 2026-07-19 | 2026-08-18 | USD | 1240.00 | 99.20 | 1339.20 | CED-1016 | high | 2026-07_fairmont-glass_invoice.pdf |

### July (month 2): Contracts

| counterparty | contract_title | effective_date | end_date | annual_value | currency | renewal_type | notice_period_days | confidence | source_file |
|---|---|---|---|---|---|---|---|---|---|
| Greenhollow Landscaping LLC | Grounds Maintenance Agreement | 2026-04-01 | 2027-03-31 | 22320.00 | USD | AUTO | 30 | high | 2026-04_greenhollow-landscaping_contract.pdf |
| Ridgeway Waste Services Inc. | Waste Collection Service Agreement | 2025-11-01 | 2026-10-31 | 11760.00 | USD | AUTO | 45 | high | 2025-11_ridgeway-waste_contract.pdf |

### July (month 2): Exceptions

| source_file | rule | detail |
|---|---|---|
| 2026-07_ridgeway-waste_invoice.pdf | 3 | invoice number RWS-660291 also appears in 2026-07_ridgeway-waste_invoice-resent.pdf |
| 2026-07_ridgeway-waste_invoice-resent.pdf | 3 | invoice number RWS-660291 also appears in 2026-07_ridgeway-waste_invoice.pdf |
| 2026-07_ashby-pest_invoice.pdf | 4 | due date 2026-07-02 is before invoice date 2026-07-20 |
| 2025-11_ridgeway-waste_contract.pdf | 6 | renews automatically; end date 2026-10-31, notice 45 days, notice window closes 2026-09-16 (42 days after the reference date) |

### July (month 2): verification numbers

- PDFs in incoming: 12
- Rows across Invoices and Contracts: 12
- Sum of the Total column on Invoices: 17,038.00 USD
- Documents flagged: 4, exception rows: 4
