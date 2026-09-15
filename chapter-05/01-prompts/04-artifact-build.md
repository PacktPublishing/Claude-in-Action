# Building the digest as an artifact

One request in Cowork, with the toggle set to Cowork. Approve the connector
access Claude asks for while it builds, and approve only what the dashboard
needs.

---

Build me a dashboard artifact called Monday Digest that shows my team's overdue and due-this-week ClickUp tasks, unanswered threads and my mentions from #client-aurora and #delivery, this week's calendar, and emails waiting on my reply. Order the sections by urgency using the same rules as my digest task.

---

## What you get, and what you do not

Opening the artifact pulls current data from the connectors, so it shows the
moment you open it rather than the moment it was built. It will not show you
last Monday's picture. The record of a given week is the saved file, which is
why Daniel keeps both.

The refresh reuses the connectors you approved when the artifact was created,
without asking again each time.

## Optional: the scheduled task updates the artifact

If you want the week to start with both a record and a current view, add one
line to the end of the scheduled task instructions in
01-digest-instructions-manager.md:

    After saving the file, update the Monday Digest artifact with the same content.
