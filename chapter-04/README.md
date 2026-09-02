# Chapter 4: Documenting your operations, turning processes into SOPs

Everything the chapter refers to: the four prompts, the samples that let you run the
whole exercise without documenting one of your own processes first, the sop-manager
skill as an uploadable zip, and the finished procedure after team review.

Rowanfield Accounting is fictional, and so is every name, document, date, and figure in
these files. Nothing here comes from a real client.

## What is in this folder

| Path | What it is |
| --- | --- |
| `sop-manager-skill.zip` | The skill, ready to upload as is through Customize \| Skills \| Add \| Upload skill |
| `sop-template.md` | The SOP template from the chapter, identical to the copy inside the skill |
| `01-project-instructions/` | The text to paste into the shared project, with placeholders for your two links |
| `02-prompts/` | The four prompts, the answer sheet for your own process, and three samples |
| `04-example-output/` | The finished SOP-003 after team review, and a sample index spreadsheet as CSV |

The skill ships as a zip only. To read or edit it, unzip it, change the files inside
the `sop-manager` folder, and rebuild the zip from that folder so the structure
survives:

```
zip -r sop-manager-skill.zip sop-manager
```

Re-upload it afterward. Anyone you shared it with gets the new version automatically.

## Before you start

- Any paid plan is enough for the first four sections of the chapter, which happen in a
  plain Chat conversation.
- The shared library needs a Team or Enterprise plan, because the project and the skill
  are shared with colleagues. On those plans, skill sharing stays off until an
  organization owner turns it on under Organization settings | Skills.
- You need the Google Drive connector enabled, and an account that can create and share
  a folder and a spreadsheet.

## Setting it up

1. Create a Drive folder named `SOPs` and share it with your team.
2. Create a spreadsheet named `SOP index` with these eight columns: ID, Title,
   Category, Owner, Last updated, Last reviewed, Status, Link. Import
   `04-example-output/sop-index.csv` for the header row, then delete the sample rows.
3. Create a shared project, paste in `01-project-instructions/project-instructions.md`,
   and replace the two placeholder links with your folder and spreadsheet links.
4. Upload `sop-manager-skill.zip` through Customize | Skills | Add | Upload skill, then
   share it with everyone who will write or update procedures.
5. Ask each of those people to enable the skill in their own list, since a shared skill
   arrives switched off.

## Running the exercise

In order: prompt `01`, then the dictated sample or your own description, then the
answers, then `05` with the template attached, then `06` with the feedback, and `08`
once a month afterward.

| File | When |
| --- | --- |
| `02-prompts/01-interview-prompt.md` | Starts a new procedure. Interview only, no writing |
| `02-prompts/02-sample-dictated-description.md` | Nadia's description, if you want to follow the chapter exactly |
| `02-prompts/03-sample-answers.md` | Her answers to both interview rounds |
| `02-prompts/04-answer-sheet.md` | What a complete reply covers, for your own process |
| `02-prompts/05-write-the-sop.md` | After the questions stop. Send with the template |
| `02-prompts/06-apply-team-feedback.md` | After the review round |
| `02-prompts/07-sample-team-feedback.md` | Four reviewers with the contradictions left in |
| `02-prompts/08-monthly-audit.md` | Once a month, plus the quarterly reconciliation question |

## The two dates

The index and the template both carry Last updated and Last reviewed, and they answer
different questions. Last updated changes only when the content of a procedure changes.
Last reviewed changes whenever an owner confirms the procedure still matches reality,
including when the answer is "still accurate, nothing changed". The audit reads Last
reviewed, so a document that was edited recently but never re-checked still comes up
when it should.

## Why you paste the index row yourself

The Google Drive connector creates and edits documents, but it cannot write into
spreadsheet cells. So the skill writes the procedure into the folder and hands you the
finished index row as text: once as a table you can check at a glance, once as a
tab-separated line that pastes into eight cells.

That step is worth keeping even when it stops being a limitation. It is where you see
the ID, the owner, both dates, and the status together, and where a status left on draft
or an owner pointing at the wrong role is obvious before it becomes the row the whole
team reads. It also means nothing enters the library quietly.

The one thing it demands is that you paste the row before you close the conversation.
The skill asks, and the quarterly question in `08-monthly-audit.md` catches whatever
slipped through anyway.
