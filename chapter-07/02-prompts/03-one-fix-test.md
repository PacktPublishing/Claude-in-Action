# Prompt 3: the one-fix test

Add this line to the extraction prompt when Claude merges two problems into one theme, or splits one problem into two:

```
Two responses belong to the same theme only if one fix would resolve both.
```

## What it catches in the Silverpine data

- **A bad merge.** SMS reminder caps and broken Romanian and Hungarian characters both mention SMS. They are a plan-limits decision and an encoding bug, owned by different teams. Raising the cap does nothing for the characters.
- **A bad split.** "The mobile page freezes" and "clients cannot book from their phones" describe the same problem in different words. One fix resolves both.

Fix the prompt, not the output. The corrected prompt is what runs next quarter. When two consecutive runs survive your audit without a correction, the prompt is done.
