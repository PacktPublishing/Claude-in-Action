# Prompt 2: theme extraction

Run this in the open, before building any skill, so you can see what comes back and argue with it.

```
Read every response in the sheet "Silverpine Feedback Form Responses".
The free text is in columns F, G, and H. Columns B, C, and D hold
business type, tenure, and satisfaction score.
1. Group the free-text feedback into themes. A theme is a distinct
problem or request, not a department or product area.
2. For every theme, report: how many responses mention it, how many
distinct respondents those represent, their row numbers, and 2-3 short
representative quotes.
3. For each theme, list the business types that reported it and how long
those customers have been with us, using columns B and C.
4. Label each theme as a complaint, a feature request, or both.
5. Rate the strongest emotion in each theme from 1 (mild) to 5 (customer
reports lost revenue or threatens to leave). Report the strongest, not
an average, and give the row it came from.
6. Never include names or email addresses in the output, and strip any
detail that could identify a customer or their business.
7. If fewer than 3 distinct respondents support a theme, list it under
"Weak signals" instead of the main analysis.
```

## Your own data

Change the sheet name, the column letters in the first three lines, and the description of a 5 in rule 5. A 5 should describe the worst outcome your customers actually report.

## Then audit it

Pick two themes, open the cited rows in the sheet, and check that the quotes exist and the counts hold. `05-answer-key/expected-results.md` has the correct numbers for every theme. Small differences in how Claude draws a theme boundary are normal; a difference of more than two or three mentions on a large theme means the prompt needs a correction, not the output.
