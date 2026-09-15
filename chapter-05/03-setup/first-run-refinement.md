# Reading your first run

Never schedule an untested prompt. Expect one or two rounds of fixes. They cost
minutes now and save you from a month of slightly wrong Mondays.

Read the first output against these five questions, one per source plus the
whole.

## ClickUp: is the task count believable?

Daniel's first run pulled every task in the workspace, because his instructions
said "my team's tasks" and his ClickUp permissions could see three other teams.

**The fix:** name your team's Space in the ClickUp source line.

    - ClickUp: all tasks in the Growth Space assigned to my team that are overdue or due in the next 7 days, with status and assignee

## Slack: did the section come back empty?

An empty Slack section on a week you know had unanswered questions usually means
one of two things: a channel name typed slightly wrong, or Claude reading
"question that got no reply" more strictly than you do, so a question answered
with an emoji reaction counts as answered.

**The fix:** confirm the channel names first, then say what unanswered means.

    - Slack: threads in #client-aurora and #delivery where a client asked something and no Bluefern person replied in the thread, from the last 7 days

## Calendar: is it listing everything?

Recurring internal holds, focus blocks, and all-day markers fill the meetings
section and push the real meetings down.

**The fix:** add them to the skip line, and say what preparation means.

    Skip: resolved threads, newsletters, calendar holds without attendees, recurring internal blocks, all-day events, and tasks in the Backlog list.

    Under meetings, list only events with at least one person outside my team, or an agenda item I own.

## Gmail: are newsletters getting through?

"Waiting on a reply from me" catches marketing mail that ends in a question.

**The fix:** scope the mail line to people.

    - Gmail: emails from the last 7 days from a real person, still waiting on a reply from me, excluding automated and marketing mail

## The whole: is it longer than a page?

Length is a filter problem rather than a writing problem. Before you ask for
shorter prose, find the section producing the most lines and tighten that
filter. Dropping the due window from seven days to five, or from all mentions to
direct questions, usually recovers the page on its own.

## When to stop

Stop when you read the digest and act on it without opening a tool to check
whether it missed something. That is the test, and it usually arrives on the
second or third run.
