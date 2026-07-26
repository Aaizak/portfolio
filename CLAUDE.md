# CLAUDE.md — Aaiza Khalid Portfolio

Project rules and conventions. Read this before making changes.

## What this is

Static portfolio site for Aaiza Khalid, product designer + engineer (~3 years
experience, positioning for a senior-leaning IC role at a startup). Rebuild of a
lapsed Webflow site. No framework, no build step — plain HTML/CSS/JS, one file
per page. Open `index.html` in a browser and it works.

## Who it's for

Hiring managers and design leads at startups, screening fast. They are looking
for two things, in this order:

1. Did she solve the right problem?
2. Can I see her judgment at the decision points?

Everything on this site should serve one of those. Process documentation that
serves neither gets cut.

## Design tokens

Do not introduce new colors or fonts. These are load-bearing — the warm
parchment palette is a deliberate reaction against the default AI/startup
portfolio look (dark mode, Inter, blue-purple accent, glassmorphism).

```css
:root{
  --bg:#F1E9DC;            /* parchment */
  --bg-card:#FBF7EF;
  --ink:#3B2A3E;           /* plum-black */
  --ink-soft:#6B5A6E;
  --ink-mute:#948298;
  --coral:#C24B2F;         /* accent, decisions, emphasis */
  --olive:#7C8A3D;         /* positive outcomes, wins */
  --border:#E2D6C4;
  --border-strong:#CBB89D;
  --font-display:'Fraunces', serif;      /* italic, display only */
  --font-sans:'Space Grotesk', sans-serif;
  --font-mono:'JetBrains Mono', monospace; /* labels, eyebrows, tags */
  --maxw:920px;
}
```

Type rules:
- Fraunces is used **italic** for display and case-study headings. Never for body.
- Space Grotesk for all body copy.
- JetBrains Mono for eyebrows, tags, labels, verdict chips. Always uppercase,
  ~11px, letter-spacing 0.06em.
- Headings are single-color. Never multi-color headings — that reads student.

## Component vocabulary

These exist and should be reused rather than reinvented. Grep for the class
names to find working examples.

| Component | Class | Where it works | Purpose |
|---|---|---|---|
| Decision callout | `.decision` | unit21 (x2), alert-scores (x1) | Coral left rule, mono "THE CALL I MADE" label, Fraunces italic title. The single highest-value component — it's what panels scan for. |
| Option toggle | `.opt-tabs` / `.opt-tab` / `.opt-panel` | unit21 three approaches | Tabbed comparison with verdict chips (`.win` olive = strength, `.lose` coral = tradeoff). Shows decision-making visually. |
| Flow stepper | `.flow-step` + `#flowimg` | bithuman 5-step flow | Click to swap screens. Replaces static flow diagrams with arrows. |
| Framed figure | `figure.framed` | unit21, alert-scores | Dark device chrome (#2A2130) with traffic-light dots. Click to zoom. Never show a floating unframed screenshot. |
| Stat band | `.stat-band` + `.n` | bithuman (x2 only) | Animated count-up on scroll. Use sparingly — two per case study max. |
| Lightbox | `.lightbox` | global | Click any framed image to zoom. |
| Scroll reveal | `.reveal` → `.in` | all case studies | IntersectionObserver, with a 400ms failsafe. |
| Cursor shadow | `.index-grid .cell` | homepage only | Shadow shifts with cursor. One signature moment, homepage only. |

## Hard rules

- **No History API.** `history.pushState` / `replaceState` throw SecurityError in
  sandboxed iframes. The single-file router uses plain show/hide. Wrap
  `scrollTo` and global listeners in try/catch for the same reason.
- **No localStorage / sessionStorage.**
- **Two stat bands per case study, maximum.** One for the problem, one for
  impact. Everything else becomes a quiet inline data-split, not a big number.
- **Never a bare screenshot.** Frame it or rebuild it natively in HTML.
- **Copy test:** if a sentence could appear on any other designer's portfolio,
  rewrite it. "Passionate about creating delightful user experiences" fails.
  "World's first prompt-to-avatar generation" passes. Named tradeoffs and real
  numbers pass. Generic craft language does not.
- **Role framing leads with ownership.** "Lead designer (solo) — also led product
  prioritization and sprint planning," not "worked with the team on."

## Files

```
index.html                    homepage, project index grid
about.html
work/bithuman.html            flagship (heavy: stepper, Kano plot, KPI table)
work/unit21.html              option toggle + 2 decision callouts
work/alert-scores.html
work/alnoor.html              archive candidate
work/tobyexpo.html            archive candidate
work/dozr.html                cut candidate
work/onboarding.html          cut candidate
aaiza-portfolio-single.html   GENERATED - all pages merged, hash router
images/                       stepper source crops (620px+ originals)
images/slim/                  recompressed for the single-file build
styles.css, script.js         legacy shared files, largely superseded by inline
```

`aaiza-portfolio-single.html` was built only to preview the site inside the
Claude chat sandbox. **In Claude Code it is obsolete** — just open `index.html`
in a browser. Do not maintain it. Delete it once you're comfortable.

## Running it

```bash
python3 -m http.server 8000   # then open http://localhost:8000
```

## Deploying

Netlify Drop (drag the folder onto app.netlify.com/drop) or `vercel`. Free,
~2 minutes. Deploy the multi-file version, not the single file — real URLs per
case study matter for sending links to recruiters.
