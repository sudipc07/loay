# Loay Nofal — Consulting Profile Site

**Date:** 2026-06-10
**Status:** Approved, building

## Goal
A single striking landing page that pitches Loay Nofal — a Manufacturing Systems
Architect — to prospective consulting clients. Substance comes from the merged
profile document; the look comes from the Stitch "Modern Industrial High-Contrast"
design system (brutalist grid + technical-schematic flavor).

## Decisions (locked)
- **Scope:** one-page long-scroll, all profile sections.
- **Theme:** dark (black base, signal-red accents) — adapted from the Stitch tokens,
  which are specified light. We invert the surface logic and keep signal red.
- **Stack:** plain static HTML + CSS + JS. No build step. Hosts anywhere.
- **Flavor:** *balanced* — bold brutalist hero/type, professional readable body.
  Keep a little schematic chrome (mono labels, section indices); drop the gimmicky
  telemetry copy (CORE_TEMP, SYNC_LATENCY, EXECUTE_CONTACT_SEQUENCE).

## Hard constraints (from the user)
- **No company names anywhere.** Industries only (medical devices, professional
  audio, industrial & mining, consumer electronics / precision measurement).
- **No email address shown.** Contact happens through the form only.
- **Contact form:** Formspree-ready. Ships with a placeholder `action`; real
  endpoint pasted in later. No mailto.

## Visual language
- Dark tokens: page `#0a0a0a`, panels `#121212`, lifted `#1a1a1a`, steel borders
  `#2a2a2a`/`#383838`, signal red `#d0291c` (deep `#ac0604`), text `#f5f7fa`,
  dim `#9aa0a8`, mono-label `#7d8590`.
- Type: Barlow Condensed (display 800–900, uppercase, tight), Hanken Grotesk (body),
  JetBrains Mono (labels/data, uppercase, +tracking). Google Fonts CDN.
- Sharp 0px corners, flat (no shadows), visible 1px borders forming a cell grid.
- Asymmetric 12-col grid; content forced into uneven spans.
- Hover = instant color inversion (panel → red), per the "mechanical toggle" spec.
- Mobile: cells stack vertically, 1px dividers preserved; headline scales down.

## Page sections (content from profile, genericized)
1. Sticky header — `LOAY NOFAL` wordmark · availability tag · `LET'S TALK` button.
2. Hero — `MANUFACTURING SYSTEMS ARCHITECT`, AI-Assisted Automation · Electronics ·
   Software, the "systems failures" thesis line, Sydney · 18 years, dual CTA,
   schematic side panel.
3. How I think — two philosophy paragraphs + pull-quote.
4. Where I fit — 4 pillars as a spec-sheet grid.
5. How I'd contribute — 5 numbered MOD-00x modules.
6. Recent outcomes — 3 case-study cards (Challenge/Approach/Outcome):
   Automated Product Validation (professional audio, featured), Global Test System
   Deployment (medical devices), Automated Calibration System (precision measurement).
7. Technical capability — dense mono spec-sheet.
8. Industry experience — 4 generic industry blocks.
9. When NOT to hire me — red-bordered warning panel (3 points).
10. Engagement model — capacity + 3 structure cards + senior-network note.
11. Contact — Formspree-ready form (Name, Company, "What problem are you solving?")
    + profile sidebar + minimal footer telemetry. No email.

## Files
```
index.html        all content, semantic sections
css/main.css      tokens + grid + components
js/main.js        mobile nav, scroll-reveal (reduced-motion aware), form stub
README.md         run + deploy + Formspree wiring notes
```

## Quality bar
Semantic HTML, labelled fields, visible red focus rings, `prefers-reduced-motion`
respected, mobile reflow keeps dividers. Verify in browser at desktop + mobile;
check dark/red contrast (WCAG AA on body text).
