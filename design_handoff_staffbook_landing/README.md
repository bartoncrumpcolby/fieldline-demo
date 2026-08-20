# Staffbook — Landing page handoff (v3)

Implement staffbook.co.uk from `Staffbook Landing v3.dc.html`. Open it in a browser — it is the spec.
All styles are inline; lift values verbatim. Brand SVGs are in `brand/`.

## What changed since the last handoff
- **Logo.** The nav top-left is the WORDMARK ALONE — lowercase "staffbook" as text (Instrument Sans 700, 22px, letter-spacing -0.03em, #21201A), linking to #top. No book mark next to it on the site; the footer repeats the same text wordmark. The book mark lives only INSIDE the product mocks' rails (cream `staffbook-mark-cream.svg` style) — that's product chrome, not site branding. `staffbook-favicon.svg` is the favicon; `staffbook-avatar.svg` is ONLY for social avatars (LinkedIn etc), never on the site.
- **Hero product mock** rebuilt to mirror the live app 1:1 (forest rail with icons, Demo Care Group pill, Insights tabs, 99% readiness, Expiring next, Latest activity, Who needs chasing). Includes the play-once cursor demo: cursor glides to Grace's overdue row, clicks (headline 2→1, chip flips green, activity logs the booking), then Evidence pack → ready ✓. Play ONCE on load, then rest at the completed state. Respect prefers-reduced-motion: skip to completed state.
- **Rota section** ("The rota, painted — not typed.") — a full-width mock matching the live rota 1:1: brush pills (DAY 1/DAY 2/MORN/TE/SE/OFF/AL/SL + dropdown + ☾ SLEEP/CLEAR), unpublished-changes banner with Publish/Discard, dashed amber cells for unpublished edits, day-cover row with red gap chips, legend row. On mobile the card scrolls horizontally (overflow-x: auto, min-width 940px).
- **Card stack** (Monday-style): six numbered cards pin + stack on scroll; left list highlights the card visually on top. On mobile the pin is disabled — cards flow normally.
- **Mid-page CTA** after the card stack; reassurance microcopy under hero CTAs ("Fifteen minutes · no card, no contract").
- **Trust chips** in the security section: UK-hosted / GDPR-aligned / No child records / Export any time.
- **Comparison strip** (spreadsheet vs Staffbook), **FAQ** (details/summary accordions), **sticky nav** with CTA, OG/meta + favicon.

## Build notes
- Fonts: Newsreader (display serif), Instrument Sans (UI), JetBrains Mono (data/labels) — Google Fonts.
- Palette: paper #F6F4EC / ink #21201A / forest #0D5C45 (CTAs, active states) / rail forest #0B3B2C / muted #5C594B / hairline #D8D4C2. App-mock neutrals are cooler: borders #E4E4E1/#EBEBE8, text #404247/#54565B/#898B91. Status: green #147A4B on #E9F3E6, amber #A96518 on #F8F0E2, red #C0392B on #F9ECE9 (each with its 1px border tone).
- All product mocks are HTML, not screenshots — keep them HTML so they stay crisp and animatable.
- Mobile-first matters most: nav collapses to logo + CTA, card stack unpins, mocks scroll horizontally, hero stacks vertically. Test at 390px.
- Scroll animation: use IntersectionObserver + position: sticky (as the spec does), no scroll-jacking libraries.
- Pricing link removed from nav deliberately — do not re-add.
