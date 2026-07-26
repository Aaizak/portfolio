# Deploy notes — what changed this session

## New file
- `work/aviary.html` — the Aviary AI case study (flagship, project 01). Fully
  interactive: two-score demo, three-level stepper, live grade widget, validation
  meter. Self-contained (images embedded, fonts from Google CDN).

## Changed files
- `index.html` — Aviary added as project 01; all other projects renumbered 02–08.
  Hero rewritten to lead with the AI-native / voice-agent identity.

## Screenshots in aviary.html are PLACEHOLDERS
The three dashboard screenshots are compressed, redacted, genericized versions.
When you have clean 2× exports (campaign names genericized, call-list contact
data redacted), swap them into the base64 data URIs in aviary.html.

## To push (in Claude Code)
1. Unzip this into your existing `site` repo folder, overwriting when asked.
2. Tell Claude Code: "Commit all changes and push to GitHub."
3. If connected to Netlify/Vercel, it deploys automatically. If not, ask Claude
   Code to set up GitHub Pages, or drag the folder to app.netlify.com/drop.

## Still TODO (future sessions — known weak spots)
- Content rework on Unit21 and Alert Scores (visual pass done, content not).
- Cut Dozr + Onboarding; compress AlNoor + TobyExpo to archive cards.
- Swap the Aviary placeholder screenshots for clean 2× exports.
