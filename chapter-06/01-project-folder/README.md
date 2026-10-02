# The project folder

Create a folder called `competitor-board` on your computer and put three files in it.

## competitors.csv

Three to five rows. The `why_it_matters` column is not decoration: Claude reads it and weights the analysis, so the giant that sets viewer expectations gets read differently than two channels of similar size with different results. Write one honest line per channel.

Point each URL at the channel, not at a single video. A video URL is the most common paste mistake and it produces odd results.

## positioning-notes.md

A few plain lines about your own company: what you sell, what the channel is for, what you publish now, and what you think the problem is. Write it in your own words. Saying you do not know what the problem is beats inventing a theory.

Describe what you actually publish, not what you meant to publish. If the notes say three long videos a month and the connector reports six uploads that are mostly Shorts, every comparison on the board is anchored to a channel that does not exist. Check the notes against your own card after the first run and fix whichever one is wrong.

## our-channel-export.csv

Your own numbers. In YouTube Studio, open **Analytics**, set the range to the last 12 months, and use the export option.

Save it in the folder under exactly the name `our-channel-export.csv`, since that is the name the prompts refer to. Leave the contents as YouTube Studio produced them.

`our-channel-export-SAMPLE.csv` in this folder shows the shape of that file. Delete it once you have your own.

If you do not run a channel, skip this file and delete the two lines about it from `02-prompts/02-competitor-breakdown.md`.
