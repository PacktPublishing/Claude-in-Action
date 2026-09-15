# Digest instructions: the manager version (Daniel)

This is the three parts from the chapter joined into the single standing
instruction you paste into the manual run, and then into the scheduled task.

Change the channel names, the folder path, and the team reference to your own
before the first run.

Nothing in this prompt says when to run it. You set the frequency and the day on
the scheduled task itself, under Frequency, so a schedule written into the
prompt would only duplicate it.

---

Build this digest.

Sources:
- ClickUp: all tasks assigned to my team that are overdue or due in the next 7 days, with status and assignee
- Slack: threads in #client-aurora and #delivery where a question got no reply, plus any message that mentions me, from the last 7 days
- Google Calendar: all meetings this week, flagging any with external attendees
- Gmail: emails from the last 7 days still waiting on a reply from me

Order the digest by urgency, not by source:
1. Overdue tasks, oldest first
2. Blocked tasks and unanswered client questions
3. Meetings in the next 48 hours that need preparation
4. Emails waiting on my reply for more than 3 days
5. Everything else, grouped by project

Skip: resolved threads, newsletters, calendar holds without attendees, and tasks in the Backlog list.

Format:
- Open with a 3-sentence summary of the week ahead
- One section per priority level, as bullet points with links back to the source items
- Add a one-line workload note per team member: how many open tasks each person carries into the week
- Keep the whole digest under one page
- Save it as a Markdown file named with today's date in my Documents/Digests folder

---

## The four lines people change first

- **The Slack channels.** Name them. Naming keeps the digest focused and keeps
  Claude out of channels that have nothing to do with your Monday.
- **The team scope.** If your ClickUp account can see other teams, add the name
  of your team's Space to the ClickUp line.
- **The folder.** Documents/Digests is the path in the chapter. Any local folder
  works, and the folder has to exist before the first run. Saving locally is what
  ties the task to your machine. Drop that line and turn off Require this
  computer on the scheduled task, and the run stops depending on your laptop
  being awake.
- **The workload line.** This is the one block the individual contributor
  version drops. See 02-digest-instructions-ic.md.
