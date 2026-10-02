# Prompt 2: the competitor breakdown

```
Use the vidIQ connector to build a competitor breakdown for each
channel in competitors.csv. For each one, pull:
- subscriber count and 90-day growth rate
- uploads per month and the split between long videos and Shorts
- average views per video over the last 90 days, and that figure as
  a percentage of subscriber count
- the three videos from the last 90 days that most outperformed
  the channel's own average, with their topics
- which topics are gaining traction on the channel

Compare each channel against our numbers in our-channel-export.csv
and keep positioning-notes.md in mind when interpreting results.
Return the results as one structured card per channel.
```

No channel of your own: delete the line beginning `Compare each channel` and the line after it, and replace them with `Keep positioning-notes.md in mind when interpreting results.`

## Read the first card before going further

Check that every field came back and that the numbers are plausible. If a field is wrong, say so plainly, for example:

```
The format split for Moon & Mat looks wrong, re-check it against
their uploads from the last 90 days.
```

Three failures are common at this point:

- A query fails or returns nothing. Check the connector status first. An expired sign-in is the usual cause, and you reconnect and rerun.
- A channel returns very little data. Check that its URL in `competitors.csv` points at the channel and not at a single video.
- The upload count disagrees with the channel's own video count. The connector counts the uploads in its per-format lists, which can exclude live streams and other upload types. Decide which number you want on the card and say so in the prompt rather than averaging the two.

Five signals go in, five fields come back on each card. If you only get four, say which one is missing and ask for it rather than rewriting the whole prompt.
