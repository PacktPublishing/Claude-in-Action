---
name: roadmap-builder
description: Builds a prioritized product roadmap from the Silverpine
  customer feedback sheet, waits for human approval, then creates a
  stakeholder presentation. Use when asked to build or update the
  product roadmap.
---

# Roadmap Builder

Turn customer feedback into a prioritized roadmap and a presentation,
with a mandatory approval step between them.

## Workflow

1. Open "Silverpine Feedback Form Responses" through the Google Drive
connector.
2. Check the folder for the most recent roadmap file. Read it in full and
read its "Data through" date. Its themes, counts, and tiers are the
starting point for this run. Analyze only responses newer than that date.
If there is no earlier roadmap, analyze every response and start empty.
3. Group responses into themes: a distinct problem or request, not a
department or product area. Two responses belong to the same theme only
if one fix would resolve both. Report mention count, distinct respondent
count, row numbers, and 2-3 short quotes per theme. Label each as
complaint, feature request, or both. Rate the strongest emotion from 1 to
5 and cite the row it came from. Using columns B and C, report the
business types and tenure range each theme spans.
4. Merge into the carried-forward roadmap: add new evidence to existing
themes and update their counts and ratings, open new themes only for
problems not already named, and keep any theme that received no new
evidence at its previous count.
5. Rank twice, once by mention count and once by count weighted by
emotion, so a 5/5 theme can outrank a more frequent 2/5 one. Show both
orders. For every theme, state its count, its emotion rating, and which of
the two orders decided its placement.
6. Draft the roadmap in three priority tiers, each item grouped under a
product area with its evidence attached, followed by a weak signals list
and a "suggested for deferral" list. Every item on that list needs one
line saying why.
7. Save the draft to the folder with the review period in the file name
and the "Data through" date at the top: the timestamp of the newest
response in this run. Do this before presenting anything.
8. STOP. Present the draft and ask for approval. Do not create any
presentation before receiving it.
9. After approval, apply any changes the user made, overwrite the saved
roadmap file with the approved version, and move anything the user
confirmed from "suggested for deferral" into "Declined or deferred".
10. Build the .pptx deck from the approved file, following the structure
in the Presentation section below. Name it with the same review period.

## Rules

- Never include customer names or email addresses in any output,
including slide notes.
- Keep quotes under 15 words and strip anything that could identify a
customer or their business: street names, business size, distinctive
services, anything that points at one person without naming them.
- Every main roadmap item must cite at least 3 rows from 3 distinct
respondents; anything with fewer goes under "Weak signals".
- Nothing enters "Declined or deferred" on your own judgment. Items you
think should wait go under "Suggested for deferral" in the draft, and
move across only when the user confirms them at approval.
- If the user changes priorities during approval, apply the change and
show the updated roadmap before building the deck.
- Generated roadmaps and decks follow the same retention schedule as the
feedback sheet. Flag any file older than that schedule when you open the
folder.

## Presentation

1. Title slide: review period and response count.
2. Method slide: data source, date range, and how items earned their
rank, including both orderings.
3. One slide per P1 item: the problem, the signal line, and at most two
customer quotes.
4. One slide grouping P2 and P3 as a watchlist.
5. Closing slide: declined or deferred items and the next review date.

Under every priority slide, write speaker notes with the full mention
count, the row references, and one sentence on what would change the
ranking.
