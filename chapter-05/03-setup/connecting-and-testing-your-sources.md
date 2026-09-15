# Connecting and testing your sources

Connect one source at a time and test it before moving to the next. A broken
connector found now is a minute of work. Found after the task is scheduled, it
is a Monday with a missing section.

Two things gate all of this. On a Team or Enterprise plan, an organization owner
has to enable each connector at the organization level before you can sign in to
it. And Chapter 1's five compliance questions apply here, before the first
sign-in rather than after, because these are live systems rather than a file you
chose to paste. Connect with the narrowest account that can do the job.

## Slack

Connect from Settings | Connectors. Then open a new chat, enable the connector
for that chat from + | Connectors | Slack, and run:

    Summarize the last ten messages in #delivery.

Swap in a channel your own account can open. A summary of real messages means
the connection works. If Claude cannot see the channel, check in this order:
the connector is toggled on for this chat, your own Slack account can open that
channel, and the organization owner has enabled Slack.

## Gmail and Google Calendar

Connect Gmail, then Google Calendar on the same account. One request tests both:

    List my meetings for this week and any emails from the last three days that I have not replied to.

Your real meetings come back grouped by day, followed by the threads still
waiting on you. This is the test shown in Figure 5.3.

One boundary to remember: Claude can search and read your mail and create drafts
in your Gmail account. At the time this book was written it cannot send mail on
your behalf. A digest only reports, so this costs you nothing here.

## ClickUp

Connect from Settings | Connectors | Discover | Search connectors, then run:

    List all tasks assigned to me in ClickUp that are due this week.

If the sign-in itself fails, the conversation to have is with whoever owns your
ClickUp workspace, since workspace admins control whether outside tools may
connect at all.

Then run the test that matters more, because it is the one that catches Daniel's
first-run problem before it reaches the digest:

    List all tasks in ClickUp assigned to anyone on my team that are overdue or due in the next 7 days.

If this returns far more tasks than your team actually has, your ClickUp
permissions reach further than you expected, and the fix is to name your team's
Space in the digest instructions. See `first-run-refinement.md`.

## Before you write the instructions

The local folder has to exist. Every instruction file in this pack saves to
`Documents/Digests`, so create it or change the path. Because the task writes a
local file, it runs in the Claude Desktop app and fires only while your computer
is awake.
