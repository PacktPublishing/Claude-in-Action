# Prompt 5: the standing refresh instruction

Add this once to the Cowork session:

```
Whenever I say "refresh", re-query the vidIQ connector
for every channel in competitors.csv, update all cards and the
combined view, update the date stamps, and add a short "changed
since last refresh" note at the top listing anything that moved
by more than 10 percent.
Do not refresh data unless 24 hours have passed since last
refresh.
```

From then on, `refresh` is the whole command.

## Tuning it

- **The 10 percent threshold** filters ordinary weekly wobble. A fast niche wants a higher number, a slow one a lower number. Change it and refresh again.
- **The 24-hour floor** stops a refresh from running when nothing can have changed.
- **A recurring slice.** If one person always wants the same cut of the board, add a line here so every refresh produces it, for example: `Also write a two-sentence summary of the change note, written for the Monday content call.`

Artifacts refresh when you open them. Disable that for this board, since no new data appears five minutes later and the refresh you want is the one you ask for.
