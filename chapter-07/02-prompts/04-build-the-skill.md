# Prompt 4: build the skill

Run this in the same session, right after an analysis you have audited and are happy with.

```
Turn the analysis we just ran into a skill called roadmap-builder, saved
in this folder. The skill must run in this order:
1. Check this folder for an existing roadmap file. If one exists, read it
in full and read its "Data through" date. Carry its themes, counts, and
priority tiers forward as the starting point, and analyze only sheet
responses newer than that date. If none exists, analyze every response.
2. Extract themes from the responses in scope, following the analysis we
just ran. Add new evidence to the themes carried forward, updating their
counts and emotion ratings, and open new themes only for problems the
earlier roadmap does not already name.
3. Rank the themes twice, once by mention count and once by count
weighted by emotion, and say which of the two decided each placement.
4. Save the draft roadmap as a markdown file in this folder, with a "Data
through" line at the top recording the timestamp of the newest response
included in this run. This step is not optional and must produce a file
before moving on.
5. Show me the roadmap and stop. Do not create a presentation yet.
6. Only after I reply with approval, update the saved file to the
approved version, then build the presentation from it.

The presentation must follow this structure: a title slide with the
review period and response count; one method slide covering the data
source and how items earned their rank; one slide per P1 item with the
problem, the signal line, and at most two customer quotes; one slide
grouping P2 and P3 as a watchlist; a closing slide with declined items
and the next review date. Under each priority slide, write speaker notes
carrying the full mention count, the row references, and one sentence on
what would change the ranking.

The roadmap and the presentation, including slide notes, must never
contain a customer name or email address, and quotes must be stripped of
anything else that could identify a person or business. Generated files
follow the same retention schedule as the feedback sheet.
```

## Read what Claude wrote

Compare the skill Claude saves against `03-skill/roadmap-builder/SKILL.md`. The wording will differ. Check these four things are present:

- The STOP before any presentation is created
- The "Data through" line, and the instruction to read the previous roadmap in full rather than only its date
- The three-respondent rule for main items
- The rule that nothing enters "Declined or deferred" without your confirmation
