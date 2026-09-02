# Prompt 4: the monthly audit

Ask this once a month inside the shared project, with the sop-manager skill enabled.

---

Which SOPs are overdue for review?

---

The skill reads the index, compares every last-reviewed date against the six-month
interval, and returns the overdue procedures grouped by owner. Each owner then either
dictates what changed or replies "still accurate", and Claude hands back the index row
to paste, with Last reviewed moved to today and Last updated left where it was.

A second question worth asking once a quarter, since the skill can read the folder as
well as the sheet:

---

Compare the documents in the SOP folder against the index and tell me
what does not match.

---

That catches the one failure this system has: a procedure written and approved, with
its index row still sitting unpasted in an old conversation.
