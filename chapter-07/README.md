# Chapter 7 materials: Building a product roadmap from customer feedback

Everything you need to run the Silverpine example end to end, then point the same workflow at your own feedback.

## What is here

- `01-feedback-data/` the Silverpine feedback sheet (189 responses, April 1 to June 26, 2026) and a second batch of 60 July responses for testing the update loop
- `02-prompts/` every prompt from the chapter, in the order you run them
- `03-skill/` a reference copy of the `roadmap-builder` skill, for comparing against the one Claude writes for you
- `04-samples/` what the outputs look like on the Silverpine data
- `05-answer-key/` the correct counts for every theme, row by row, so you can audit Claude's analysis

## Before you start

- A Claude account on any paid plan, with the Claude Desktop app installed
- The Google Drive connector enabled
- A folder on your computer called `silverpine-roadmap`
- The Claude mobile app, only for the Dispatch section

## A note on the data

Silverpine Scheduling, its customers, and every response are fictional. The email addresses all use `example.com`, `example.net` and `example.org`, which are reserved for documentation and reach nobody.

The sheet is built so that every number in the chapter holds: 30 deposit mentions from 24 respondents, 27 mobile mentions, 19 sync mentions, the yoga studio owner writing in three months running, and so on. If Claude reports something different, `05-answer-key/` tells you whether Claude or the prompt is wrong.
