# CONTEXT.md — where this project stands

Handoff from the Claude chat sessions. Everything decided, everything still
open. Read alongside CLAUDE.md.

---

## Situation

Aaiza Khalid — product designer + engineer, ~3 years experience, targeting the
perception of 5+. Currently on maternity leave with roughly 1.5 months left
before returning to a job search. Baby is ~1.5 months old, so working time is
fragmented and scarce. Optimize for high-leverage work, not completeness.

Target roles: IC product design at startups, ideally AI-native ones.

Old site: https://portfolio-bb584f.webflow.io/

## Assets

- LinkedIn: https://www.linkedin.com/in/aaizakh/
- Resume: https://drive.google.com/file/d/19e17WvqtgwXd5ikh0A21keDAwqfaJ39k/view
- Signature image: https://cdn.prod.website-files.com/6029a00655b62debcb2ac54f/608301ea3f40d42e7179f87a_signature%20(4).png
- bitHuman demo video: https://cdn.prod.website-files.com/6029a00655b62debcb2ac54f/68279f8897123caac92171d0_1726096624554-transcode.mp4
- Email: aaiza_khalid@hotmail.com

Most case-study images are still hosted on the old Webflow CDN
(`cdn.prod.website-files.com`). They work, but they're a dependency on an
account that may lapse. Worth re-hosting eventually.

---

## Decisions already made

**Visual direction — "merged light + warm."** Parchment background, plum ink,
coral and olive accents, Fraunces italic display. Chosen over a dark
alternative specifically to avoid the Linear/Vercel aesthetic that now reads as
AI-generated. See CLAUDE.md for tokens.

**Curation.** Seven case studies is too many; 3–5 is the consistent
recommendation. Planned flagship order:

1. **Aviary AI** — not yet written. See below.
2. **bitHuman** — recent, visually strong. Aaiza has reservations (see below).
3. **Unit21** — strongest decision-making narrative.
4. **Alert Scores** — solid, shows AI/trust thinking.

Compress AlNoor and TobyExpo into small archive cards. Cut Dozr and Onboarding
entirely — internship and dev-era work lowers the perceived ceiling.

**Homepage hero needs a rewrite.** Currently category-generic. Should be built
around an AI-native / voice-agent / AI-trust identity, with Aviary as project 01.

**Role framing.** Lead with ownership everywhere. bitHuman reads "Lead designer
& frontend (solo design)." Aviary should read as lead solo designer plus product
and sprint leadership.

---

## Research findings that drove the above

**How portfolios actually get screened.** Click link → judge visual craft within
seconds → scan hero for role fit → skim work for clarity of thinking → check who
you are. The hero statement does more work than any case study.

**What hiring managers say they want.** Judgment, clarity of reasoning, and
impact — not process documentation. A portfolio that shows *why* decisions were
made reads as a different candidate from one that shows screens and steps. This
is the entire justification for the `.decision` component.

**The AI-sameness problem.** Recruiters now report generic AI-looking portfolios
as an active negative signal. The visual fingerprint: rounded cards, soft
shadows, stat row across the top, blue/purple accent, modern grotesque sans,
bento grids, glassmorphism. The copy fingerprint: polished sentences that could
belong to anyone. This site is deliberately built against that.

**Curation.** 3–5 projects. More dilutes signal.

---

## Work completed

Visual pass across the site:

- **bitHuman** rebuilt as the showcase page — hero video in a device frame, two
  stat bands with animated counters, native HTML KPI table, Kano scatter plot
  (SVG, features plotted by category), interactive 5-step flow stepper with
  lightbox, four testing-learning quote cards, scroll reveals.
- **Unit21** — three discovery approaches converted into a tabbed comparison
  with win/lose verdict chips; two decision callouts ("To automate, or not?"
  and "Reversing my own decision"); all 12 figures framed with click-to-zoom.
- **Alert Scores** — framed figures, lightbox, reveals, one decision callout
  ("Scores inform — they don't decide").
- **Homepage** — entrance cascade on hero text, cursor-following shadow on
  project cells as the site's one signature interaction.

---

## Open items

### 1. Aviary AI case study — the biggest gap

Roughly one year as lead solo designer at a voice-agent company, also running
product prioritization and sprint planning. It is the most recent and most
senior work and it is **entirely missing from the portfolio**. Nothing else on
this list matters as much.

Known shape of the story: users weren't monitoring their voice agents →
email re-engagement → in-product performance transparency.

Source material is on Aaiza's other laptop. Needed: product context, the
monitoring problem with real numbers, what was designed, what moved, and the
specific decisions and tradeoffs along the way.

### 2. bitHuman — resolve the reservation before polishing further

Aaiza has said she doesn't like this case study but feels obligated to include
it because it's recent. This is unresolved and matters more than it sounds: a
case study she doesn't believe in is one she'll interview badly on, and panels
read hedging as weak ownership.

The diagnosis question, still unanswered — which of these is it?

- The problem was handed to her, so the framing feels borrowed
- The outcome numbers are soft, projected, or landed after she left
- She was executing someone else's product direction; the real calls weren't hers
- Visually impressive but the underlying thinking was thin
- It's fine and she's just sick of looking at it

Each implies a different fix: reframe, re-source the numbers, foreground the
decisions that *were* hers, rebuild the thinking, or leave it alone.

### 3. Content critique not yet done

The visual pass is complete; the content pass hasn't started. For bitHuman and
Unit21, work through:

- Is the problem framing sharp, and is it clear *she* found the problem?
- Are the key decisions visible, with the alternatives she rejected?
- Are there gaps in research, tradeoffs, or impact evidence?
- Does any sentence read as generic enough to belong to another designer?

### 4. Image quality

Six archetypes across the site, and the fix for each:

1. macOS Figma screenshots (bitHuman) → rebuild informational content natively
   in HTML; re-export the rest at 2x
2. Flow diagrams with arrows → interactive stepper (pattern proven on bitHuman)
3. Iteration comparisons (Unit21, AlNoor, Dozr, TobyExpo) → option toggle with
   verdict strip (pattern proven on Unit21)
4. Hand-drawn user-story stickies (Unit21) → HTML quote cards
5. GIF walkthroughs (AlNoor x4, TobyExpo x3) → re-record as MP4 **if the source
   Figma prototypes still exist — unconfirmed**
6. Hero images → device frame with outcome stat overlay

Roughly 6–8 key images need re-export from Figma at 2x. Exact list not yet
determined.

Why the old site read young, for reference: multi-color heading system, rounded
playful typeface, cutesy illustrated avatars, pastel affinity boards, unframed
floating screenshots. These are visual-language problems, not resolution
problems — upscaling would not have fixed them.

### 5. Verify the Kano plot

The bitHuman scatter plot places features by category:

- Attractive (olive): guided exploration, voice preview, one-click regenerate
- Performance (coral): generation speed, visual variety
- Must-be (gray): prompt generation, preview before launch, save & deploy

Aaiza needs to confirm these match the actual research, since she'll have to
defend the placement in an interview.

### 6. Remaining build work

- Roll the component vocabulary across Alert Scores and the archive pages
- Build the before/after drag slider (specced, not built) for redesigns
- Sticky mini-TOC on long case studies (specced, not built)
- Rewrite the homepage hero
- Compress AlNoor and TobyExpo to archive cards; remove Dozr and Onboarding
- Deploy

---

## Technical notes worth keeping

The single-file build (`aaiza-portfolio-single.html`) exists only because the
Claude chat preview sandbox can't resolve links between separate files. It is
**not needed in Claude Code** — open `index.html` directly.

The bug that cost three rounds of debugging: navigation was failing with
`SecurityError: Failed to execute 'replaceState' on 'History'` because
sandboxed iframes run on an opaque origin and forbid URL rewriting. The router
now uses plain show/hide with no History API. Lesson: read the console first.

The five stepper images are local crops with no public URL, which is why they
were base64-embedded. Once the site is deployed they can be referenced normally.
Originals are in `images/`, recompressed copies in `images/slim/`.
