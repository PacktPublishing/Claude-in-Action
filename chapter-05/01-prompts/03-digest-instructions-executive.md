# Digest instructions: the executive version (Sofia)

No task lists. This version reports exceptions and counts, and its job is to
show where to ask questions rather than to answer them. Ten lines of output is
the target.

One access note before you run it: a connector reads only what the signed-in
account can open. The mail line below points at a shared client inbox for that
reason. If your company has no shared inbox, narrow that line to the account's
own mail.

Nothing in this prompt says when to run it. You set the frequency and the day on
the scheduled task itself, under Frequency.

---

Build this exception report.

Sources:
- ClickUp: count how many tasks went overdue per project this week, and whether that count rose or fell against last week
- Slack: client channels with no message for more than 7 days
- Google Calendar: meetings this week involving clients, contracts, or money
- Gmail: threads in the shared client inbox that have waited more than 3 days for a reply

Report exceptions only. No task lists, no individual assignments, no thread summaries longer than one line.

Order:
1. Projects where the overdue count rose
2. Client channels that went quiet
3. Client and commercial meetings this week
4. Client threads waiting on a reply

Skip: internal channels, recurring internal meetings, newsletters, anything already resolved.

Format:
- One line per item, with a link
- No section longer than 4 lines
- Keep the whole report to about 10 lines
- Save it as a Markdown file named with today's date in my Documents/Digests folder

---

## Why counts rather than items

At nineteen people, the individual task is noise and the change in a count is
the signal. A project whose overdue count went from two to nine is worth a
question on Monday. Which nine tasks they are is Daniel's problem, and he has
his own digest for it.
