# Reference routine instruction

Claude writes its own version of this text when you ask for the routine, and the wording will differ. Use this one to check that yours covers the same steps and the same safety rules. You can also paste it directly if you prefer.

```
You run unattended in the cloud. Use only the Airtable, Hunter, and Slack connectors. Do not create files or folders.

1. Open the Fernwell Sales base in Airtable. Read the Config table. Take the Value of the row with Key "ICP" as the scoring rules and the Value of the row with Key "ALERT_FORMAT" as the alert layout. If either row is missing or empty, send me a Slack direct message saying which one, and stop without reading, scoring, or updating any Prospects row.

2. In the Prospects table, select only the rows where Status is empty. If there are none, send me a Slack direct message saying "No new prospects today" and stop.

3. Enrich the selected rows one company at a time, never in bulk. For each row with a domain, look up the domain through the Hunter connector and take the industry or category, the employee range, the city and country, and the technologies list. Write them to Industry, Employees, City, Country, and Tech. If the row has no domain, or Hunter returns no match, set Status to "Needs human", write the reason in Reasons, and move to the next row. Never guess or fill in data Hunter did not return.

4. Score every enriched row against the ICP rules from Config. Score only from data Hunter returned. A borderline or ambiguous field scores zero for that criterion and is noted in Reasons. Do not round scores up. Write Score, Tier, and Reasons, where Reasons is one line naming the criteria that earned points. Rows marked "Needs human" get no score and no tier.

5. For every A-tier company, send me a Slack direct message in the ALERT_FORMAT layout. Send all "Needs human" rows from this run as one grouped Slack message, labeled "Needs human", listing the company, the domain if there is one, and the reason.

6. For every scored row, set Status to "Processed" and Processed Date to today. For every "Needs human" row from this run, set Processed Date to today. Never change the Company, Domain, Source, or Date fields.

7. If anything fails partway, leave Status empty on every row you have not finished, so the next run picks them up, and report the failure in the run summary.

8. Send me a Slack direct message with the run summary: how many companies processed, how many per tier, and how many came back "Needs human".

You never contact a prospect company, by email or any other channel. Your only messages go to me in Slack.
```

## The five checks from the chapter

- The ICP and alert format are read from Config (step 1), not copied into the text.
- Only rows with an empty Status are selected (step 2).
- Enrichment runs one company at a time (step 3).
- The no-match path and the never-guess rule are there (step 3 and step 4).
- Nothing lets the routine contact a company (the last line).
