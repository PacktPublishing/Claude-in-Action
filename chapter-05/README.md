# Chapter 5 companion pack

Project 4: building an automated Monday morning digest.

Everything the chapter asks you to type, plus a finished digest to compare your
own against. All of it is plain Markdown, so you can open, edit, and paste from
any text editor.

## What is here

    01-prompts/
      01-digest-instructions-manager.md      the full standing instruction (Daniel)
      02-digest-instructions-ic.md           the individual contributor version (Amara)
      03-digest-instructions-executive.md    the exception report (Sofia)
      04-artifact-build.md                   build the dashboard version
      05-maintenance-prompts.md              the ten minutes a month

    02-example-output/
      2026-10-26.md                          a finished digest from Daniel's Monday
      README.md                              how to read it against the instructions

    03-setup/
      connecting-and-testing-your-sources.md  connect each source and prove it works
      first-run-refinement.md                 what to look for in your first output

## The short path

1. Work through `03-setup/connecting-and-testing-your-sources.md`, one source at
   a time, testing each before you move on.
2. Edit `01-prompts/01-digest-instructions-manager.md` for your channels, your
   team, and your folder.
3. Run it manually in Cowork and compare against `02-example-output/2026-10-26.md`.
4. Fix what `03-setup/first-run-refinement.md` turns up, then run it again.
5. When the output is a digest you would actually read, create it as a scheduled
   task and set Frequency to weekly on Monday, at a time your computer is awake.
   The prompts here carry no schedule of their own, by design.

Daniel's whole build took about four hours, most of it connector approvals and
two rounds of fixing the instructions. Colleagues who start from working
instructions spend about fifteen minutes each.

## Two things to change before your first run

**The folder.** Every instruction file saves to `Documents/Digests`. Point it
somewhere that exists on your machine. Because the task writes a local file, it
runs in the Claude Desktop app and fires only while your computer is awake. Drop
that save line and turn off Require this computer on the scheduled task, and the
run stops depending on your laptop.

**The channels.** `#client-aurora` and `#delivery` are Bluefern's. Yours will be
different, and naming them is what keeps the digest focused.

## About the example company

Bluefern Digital is a fictional 19-person marketing agency. Sofia Marchetti,
Daniel Reyes, Amara Osei and their four colleagues are invented, as is every
task, thread, meeting, and link in the example digest. The connectors, the
instructions, and the schedule are the parts you will set up for yourself.
