# Chapter 10 companion pack: Enriching and qualifying leads automatically

This folder holds everything you need to follow Project 9 with the same data the chapter uses.

## What's inside

- `01-sample-data/prospects-sample.csv`: seven real companies for the Prospects table, including one row with no domain and one company above the size ceiling.
- `02-prompts/prompts.md`: every prompt from the chapter, in the order you type them.
- `03-config-values/`: the two values that go into the Config table, `icp.txt` and `alert-format.txt`.
- `04-answer-key/`: the tiers the sample companies should land in, and a reference routine instruction to compare against the one Claude writes for you.
- `05-optional-skill/lead-qualification/`: the pipeline packaged as a skill, for once your scoring has settled.

## How to use it

1. Follow the chapter's setup steps until step 4.
2. In step 4, ask Claude to add the rows from `prospects-sample.csv` (the prompt is in `prompts.md`).
3. Paste the prompts from `prompts.md` as you reach each one in the chapter.
4. After scoring, compare your Score, Tier, and Reasons columns with `04-answer-key/expected-results.md`.

The companies are real so that Hunter has something to find. Hunter's data changes over time, so your employee ranges and technologies may differ from the answer key. When they do, check that the score follows from what Hunter returned, not that it matches the key exactly.
