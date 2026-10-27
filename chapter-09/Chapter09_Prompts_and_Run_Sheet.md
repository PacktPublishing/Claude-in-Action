# Chapter 9 – Prompts and run sheet

Every prompt from Chapter 9, in the order the chapter uses them, plus the answers to give at each skill step so the run matches the text. Prompts are copied exactly as printed in the chapter.

## 0. Setup (once)

1. Unzip `lakemont-site.zip` into a working folder, for example `Documents/chapter-09/`. You get `lakemont-site/` with `brand/`, `copy/`, and `media/`.
2. Optional: put 3 or 4 of your own photos in `lakemont-site/media/` (team, treatment room). Without them, both paths place Unsplash images marked `SWAP:`.
3. Create an **empty** folder next to it: `Documents/chapter-09/lakemont-physio/`.
4. Make sure Chrome (or Edge) is installed; the skill uses it for the mobile check and screenshots.
5. Have GitHub and Vercel accounts ready (free), or create them during publishing.

Final layout:

```
chapter-09/
├── lakemont-site/      ← input pack (brief, logo, photos)
└── lakemont-physio/    ← empty build folder
```

---

## Path A: Claude Design

### A1. Create the design system

Click **New**, then **+ | Design system | New design system**. Choose Claude chat, set the company name to **Lakemont Physio**. Attach `brand/logo.svg`, `copy/brief.md`, `copy/testimonials.md`, and the photos from `media/` (if any). Then send:

```
Build a design system for Lakemont Physio from the attached files. Extract the colors, fonts, components, and layout patterns.
```

Review the result. Confirm it by searching its name on the **Artifacts** page.

**No-brand variant** (the chapter's alternative to step 3):

```
Lakemont Physio is a two-therapist physiotherapy clinic in central Lakemont. Our patients are office workers and recreational athletes, 25-60. Propose two or three visual directions for our brand.
```

### A2. Generate the page

Start a new design with the Lakemont design system selected, attach `copy/brief.md`, and send:

```
Build a one-page website for Lakemont Physio using the attached brief. Sections: hero, trust strip, services, why us, area, testimonials, FAQ, final call, footer. The one action on the page is "Book an assessment", linked to cal.com/lakemont, repeated in the top bar, hero, and final call. Calm, professional, no ad-speak.
```

### A3. Refine (the three levers, in order)

Chat (broad changes), one at a time:

```
make the color scheme warmer
```
```
tighten the spacing between sections
```
```
rewrite the hero for someone in pain right now.
```

Inline comment (for Figure 9.3): click the hero headline and write, for example:

```
Make this headline name the problem: back pain, sports injuries, recovery after surgery.
```

Direct edits: fix a typo in place, drag, resize, or align, then ask Claude to apply the change across the design.

Explore a variant without losing the current version:

```
save this version, then try a darker, more clinical direction.
```

### A4. Hand off to Claude Code

Use the Claude Code handoff from the design's export options (see the screenshot notes about checking the exact labels). In Claude Code, continue with section B6 (review) and B8 (publishing).

---

## Path B: the one-shot-website skill

### B1. Install the skill

In the Claude app: Code icon (**</>**) → **New** → choose the empty `lakemont-physio` folder. Move `one-shot-website.zip` into that folder, then send:

```
The one-shot-website.zip skill is in this folder. Install it, then delete the zip.
```

Then type:

```
/one-shot-website
```

When the introduction appears, press **Stop** (or **Esc**).

If `/one-shot-website` isn't recognized right after the install, start a new session in the same folder (Code icon → New → `lakemont-physio`) and type it again.

### B2. Run the build

```
/one-shot-website
```

**Step 1 of 8**, answer:

```
My brief, logo, and photos are in the lakemont-site folder next to this one: the brief in copy/, the logo in brand/, and the photos in media/. Use them.
```

Alternatively you can drop the files into the chat window and modify the prompt accordingly.

Allow Claude Code to read the folder when it asks.

**Step 3 of 8** (only if the skill asks for something missing): answer what it asks. Usual answers:
- voice: `We`
- site language: `English`

### B3. Step 4 of 8: the look

The preview page opens in the browser with five directions. Pick the number of the calm teal, off-white option.

**To reproduce the chapter exactly** (name, hex codes and fonts in the plan block), choose **8 (Write my own)** and send:

```
Sage Harbor: background #F6F8F6, accent #2F7D6D, text #17302B, cards #FFFFFF, secondary text #4B5F5A. Headings in Plus Jakarta Sans, body in Inter. Off-white, calm teal, and a clean sans-serif.
```

If you pick a generated direction instead, update the chapter's direction name, the four hex codes, and the fonts in the plan block and the Figure 9.5 caption to match your run.

### B4. Step 5 of 8: sections

The chapter says Lakemont skipped "How it works". If the skill proposes it, answer:

```
Remove How it works. Keep the rest.
```

### B5. Step 6 of 8: the plan

Check that the top of the plan matches the chapter's block, then confirm:

```
Build it.
```

Step 7 runs on its own (a few minutes). For Figure 9.4, take the screenshot while files like `Hero.jsx` and `FAQ.jsx` appear in the output.

### B6. Review

```
run locally
```

Work through the review checklist in the browser at the local address.

### B7. Targeted refinements (from the chapter)

Send one at a time and re-check the section after each:

```
In the hero, change the headline to "Back pain that finally gets a plan" and keep the subline as it is.
```
```
In the FAQ, replace the payment question with: "Do I need a referral?" Answer: "No. You can book an assessment directly, no referral needed."
```
```
The photo in the Why us section shows a gym, and we are a clinic. Replace it with a calmer treatment-room image, and mark where I can swap in our own photo.
```

These three are illustrations. If your generated FAQ has no payment question, or the Why us photo isn't a gym, adapt the wording to what's on your page (for example "replace the third question with...").

### B8. Publishing (Step 8 of 8)

When the skill asks "Do you want me to put the site online now?", answer `1`. Or, any time later, from the project folder:

```
/one-shot-website publish
```

Without the skill:

```
publish this site through my GitHub and Vercel accounts.
```

If a connector is missing: **+** in the message box → **Connectors** → add GitHub / Vercel, authorize, then tell Claude it's done.

Manual step on vercel.com: open the `lakemont-physio` project → **Connect Git Repository** → authorize the Vercel GitHub App if prompted → select the repo → confirm.

Domain question: answer `2` (Not now), unless you're capturing the domain steps.

For Figure 9.6, capture the message that shows the two addresses (repository and `lakemont-physio.vercel.app`).

### B9. Placeholders and later updates

Photos added after launch (from the "Brand assets" section):

```
the logo and three team photos are in media/, put them in place of the placeholders.
```

The prompt says `media/`, so create a `media/` folder inside `lakemont-physio/` and put the files there first (or write the full path, `../lakemont-site/media/`).

An update, in the same targeted style (example):

```
In the Area section, change the Saturday hours to 9:00-14:00, check it locally, then publish again.
```

### B10. The same move, applied everywhere (one run each, in a new empty folder)

```
one page for our new posture assessment package, primary action: book an assessment
```
```
one page introducing our two therapists, primary action: apply by email
```
```
one page for our March back-health workshop, primary action: join the waitlist
```
```
one page presenting our back-health webinar, primary action: watch the recording
```

### B11. Demo mode (mentioned in the chapter)

In another empty folder:

```
/one-shot-website demo
```

or, for a specific type:

```
/one-shot-website demo restaurant
```
