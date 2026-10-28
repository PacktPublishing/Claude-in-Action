# Expected results for the sample companies

Each sample company was picked to test one part of the scoring. The table shows the points and tier each one landed on in a test run on 2026-10-28, using the data Hunter returned that day.

| Company | What it tests | Expected points | Expected tier |
|---|---|---|---|
| Pepper Construction Group | Right-sized US construction firm | Industry 30, size 30 (1K-5K), geography 20. Tech 0: no construction management or ERP tool in the list. | A (80) |
| Willmott Dixon | Right-sized UK construction firm | Industry 30, size 30 (1K-5K), geography 20. Tech 0. | A (80) |
| Kiewit | Large contractor above the size ceiling | Industry 30, geography 20, tech 20 (SAP and Oracle in the list), size 0 (10K-50K) | A (70) |
| Kodiak Building Partners | US building supplies distributor | Size 30 (251-1K), geography 20. Industry 0: Hunter returned no industry, only NAICS and SIC codes. Tech 0. | B (50), or A (80) if Hunter returns an industry |
| Duolingo | Right size and country, wrong industry | Size 30 (1K-5K), geography 20. Industry 0: Hunter returned no industry. Tech 0. | B (50) |
| Hansen Yuncken | Construction firm outside the listed countries (Australia) | Industry 30, size 30 (251-1K), geography 0. Tech 0. | B (60) |
| Harbor Lane Builders | Row with no domain | Not scored | Needs human, reason "no domain" |

## How to read your own results

Your numbers may differ from this table, because Hunter's data changes. Check each row this way instead:

1. Read the Reasons column and confirm each criterion that earned points matches a field Hunter actually returned.
2. If an employee range straddles the 8,000 ceiling (for example, 5,001 to 10,000), the size criterion should score zero and Reasons should say the range was ambiguous.
3. If the industry comes back as something broad, such as "Business services", or comes back empty, industry fit should score zero and Reasons should say so. Claude should not fill an empty industry from Hunter's tags, description, or classification codes.
4. Harbor Lane Builders should never reach Hunter. If Reasons mentions a Hunter lookup for it, the no-domain rule did not work.

After the final stage, Slack should hold one alert per A-tier company and one grouped "Needs human" message listing Harbor Lane Builders.
