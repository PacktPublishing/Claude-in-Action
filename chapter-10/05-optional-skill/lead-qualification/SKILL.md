---
name: lead-qualification
description: Runs the Fernwell lead qualification pipeline on demand. Reads unprocessed companies from the Prospects table in the Fernwell Sales Airtable base, enriches each one through the Hunter connector, scores it against the ICP stored in the Config table, sends A-tier alerts and a grouped "Needs human" message to Slack, and writes the results back to Airtable. Use this skill whenever the user asks to "qualify leads", "run the pipeline", "score the new prospects", "process the Prospects table", "run lead qualification now", or wants the morning routine to run between scheduled runs, even if they don't name the skill.
---

# Lead qualification

Run the same pipeline the morning routine runs, on demand. Use only the Airtable, Hunter, and Slack connectors. Do not create files or folders.

## Before you start

Open the Fernwell Sales base and read the Config table. Take the Value of the row with Key "ICP" as the scoring rules and the Value of the row with Key "ALERT_FORMAT" as the alert layout. If either row is missing or empty, tell the user which one and stop. Do not score against rules you wrote yourself, because the user retunes the scoring by editing that cell.

## Steps

1. Select only the Prospects rows where Status is empty. If there are none, say so and stop.
2. Tell the user how many rows you found and ask whether to continue. A bad import can add hundreds of rows, and each enrichment spends Hunter credits.
3. Enrich one company at a time, never in bulk. For each row with a domain, look it up through Hunter and write the industry or category, employee range, city, country, and technologies to Industry, Employees, City, Country, and Tech. If there is no domain, or Hunter returns no match, set Status to "Needs human", write the reason in Reasons, and move on. Never guess or fill in data Hunter did not return.
4. Score each enriched row against the ICP. Score only from data Hunter returned. A borderline or ambiguous field scores zero for that criterion and is noted in Reasons. Do not round scores up. Write Score, Tier, and Reasons, with Reasons as one line naming the criteria that earned points. "Needs human" rows get no score and no tier.
5. Send each A-tier company to the user as a Slack direct message in the ALERT_FORMAT layout. Send all "Needs human" rows as one grouped message, labeled that way, listing the company, the domain if there is one, and the reason.
6. Set Status to "Processed" and Processed Date to today on every scored row. Set Processed Date to today on every "Needs human" row from this run. Never change Company, Domain, Source, or Date.
7. If anything fails partway, leave Status empty on every unfinished row and report the failure.
8. Finish with a run summary in the chat: companies processed, count per tier, and how many came back "Needs human".

## Limits

Never contact a prospect company by email or any other channel. The only messages this skill sends go to the user in Slack.
