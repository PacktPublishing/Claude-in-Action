# Chapter 10 prompts, in order

Type these in the Code tab session you started in the setup steps. Each heading names the chapter section where the prompt appears.

## Setting up, step 3: create the base

```
Using the Airtable connector, create a base called Fernwell Sales with two tables. The first table, Prospects, has these columns: Company (single line text), Domain (single line text), Source (single line text), Date (date), Status (single select with two options, "Processed" and "Needs human", and no default), Industry (single line text), Employees (single line text), City (single line text), Country (single line text), Tech (long text), Score (number, no decimals), Tier (single select with options A, B, and C), Reasons (long text), and Processed Date (date). The second table, Config, has two columns: Key (single line text) and Value (long text). Leave Config empty. Confirm the base ID when you finish.
```

## Setting up, step 4: add the sample companies

```
Add these companies to the Prospects table. Fill in only Company, Domain, Source, and Date. Leave Status and every enrichment column empty. If a row has no domain, leave Domain empty.

Company,Domain,Source,Date
Pepper Construction Group,pepperconstruction.com,Referred by a supplier,2026-11-23
Willmott Dixon,willmottdixon.co.uk,Trade show booth,2026-11-24
Kiewit,kiewit.com,Contact form,2026-11-25
Kodiak Building Partners,kodiakbp.com,Capabilities PDF download,2026-11-26
Duolingo,duolingo.com,Newsletter signup,2026-11-27
Hansen Yuncken,hansenyuncken.com.au,Contact form,2026-11-28
Harbor Lane Builders,,Trade show booth,2026-11-30
```

## Setting up, step 6: confirm Claude sees the data

```
Using the Airtable connector, open the Fernwell Sales base, Prospects table, and tell me the columns and how many rows have an empty Status.
```

Expected answer with the sample data: 14 columns and 7 rows with an empty Status.

## Adding Hunter as a custom connector, step 7: test the connector

```
Using the Hunter connector, look up pepperconstruction.com and tell me the industry, employee range, and country.
```

## Enriching the first three companies

```
For the first three rows in the Prospects table with an empty Status, enrich each company through the Hunter connector using its domain. Pull the industry or category, the employee range, the city and country, and the technologies list. Enrich one company at a time, never in bulk. If a row has no domain, or Hunter returns no match for the domain, set its Status to "Needs human", write the reason in Reasons, and skip it. Never guess or fill in data Hunter did not return. Show me what you got for each company before you write anything back to Airtable.
```

After you check the three profiles, release the rest:

```
Now enrich the remaining unprocessed rows the same way.
```

## Commissioning the scoring stage

```
Now score every enriched company against this ICP, and save the ICP into the Config table as a row with Key "ICP" so it is stored in one place: Fernwell Systems sells inventory management software to wholesale distributors and construction firms that run large material operations. Score each company out of 100. Industry fit, 30 points: construction, civil engineering, building supplies, or wholesale distribution. Company size, 30 points: employee range of 200 to 8,000, with anything above 8,000 scoring zero on this criterion. Geography, 20 points: head office in the United States, Canada, the United Kingdom, or an EU member state. Buying-tech signal, 20 points: the technologies list shows a construction management or ERP tool such as Procore, SAP, Oracle, or CMiC. Tiers: A is 70 and up, B is 40 to 69, C is below 40.

Rules: score only from data Hunter returned, and do not infer missing data. A borderline or ambiguous field scores zero for that criterion and is noted in Reasons. Do not round scores up. Rows marked "Needs human" are not scored and get no tier. Write Score, Tier, and Reasons back to each Prospects record, where Reasons is one line naming the criteria that earned points.
```

## Checking the scores against your own judgment

```
Show me each company's Score, Tier, and Reasons in a table so I can sanity-check the scoring.
```

Compare the result with `04-answer-key/expected-results.md`.

## Connecting Slack: test message

```
Using the Slack connector, send me a direct message that says "Test".
```

## Commissioning the final stage

The alert layout is in `03-config-values/alert-format.txt`. Paste it where the prompt says.

```
Now post the alerts, and save this format into the Airtable Config table as a row with Key "ALERT_FORMAT": [paste your alert layout here]. For every A-tier company, send me a Slack direct message in that format. Send all "Needs human" rows as one grouped message instead, labeled that way rather than with a tier, listing the company, the domain if there is one, and the reason. Then update every scored record: set Status to "Processed" and Processed Date to today. Leave "Needs human" rows with that Status, and set their Processed Date to today as well. Never change the Company, Domain, Source, or Date fields.
```

Then the health check:

```
Give me a run summary: how many companies processed, how many per tier, and how many came back "Needs human".
```

## Packing it into a routine

```
Write me a single routine instruction that reproduces everything we just did, start to finish, on any unprocessed rows in the Prospects table. It has to be self-contained and run unattended in the cloud with no files and no folders: read the ICP and the alert format from the Config table, enrich through Hunter, score, send the Slack messages, write the results back, and post the run summary. Give me the text to paste, nothing else.
```

If the routine Claude writes is missing either of the two safety behaviors from the chapter, ask for them:

```
Add two behaviors to the routine. First, if the ICP or ALERT_FORMAT row in Config is missing or empty, stop and report it without scoring or updating any row. Second, if the run fails partway, leave the Status of every row it has not finished empty, so the next run picks them up. Give me the full corrected text.
```

## Testing the routine again

The routine only processes rows with an empty Status, so after your first run it finds nothing to do. To test it again, add a fresh row:

```
Add one company to the Prospects table: Company "Mortenson", Domain "mortenson.com", Source "Contact form", Date today. Leave every other field empty.
```
