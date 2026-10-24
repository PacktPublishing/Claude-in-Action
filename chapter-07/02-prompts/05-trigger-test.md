# Prompt 5: trigger test

In a new conversation with the toggle set to Cowork and the same folder selected:

```
Build the product roadmap
```

Claude should say it is using the `roadmap-builder` skill and start at step 1. If it does not, open the skill file and add the phrase you used to the `description` field. Claude reads the description to decide whether a skill fits the request.
