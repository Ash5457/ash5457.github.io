# Design System: akashbahl.com

## Overview

A case file with a terminal voice. The page is laid out like an evidence file: left-aligned, one statement headline, then projects presented as claims with their proof beside them. The terminal from the GitHub and LinkedIn headers appears as one framed object per section (the fastfetch summary in the hero, one summary block per project). Prose is set in a sans face. Monospace is used only where a terminal would really print the text: prompts, commands, file names, key and value output.

Audience: recruiters and hiring managers for help desk, desktop support and field service roles, who give the page well under a minute, plus technical interviewers who will click through to the evidence.

## Colors

Taken from `scripts/build_header.py` in the profile repo. Dark only, by brand.

| Token | HEX | Use |
|---|---|---|
| `--bg` | `#0d1117` | Page and terminal body |
| `--surface` | `#161b22` | Terminal title bar, command chips |
| `--line` | `#30363d` | All borders and rules, 1px |
| `--strong` | `#f0f6fc` | Headings |
| `--text` | `#c9d1d9` | Body text |
| `--muted` | `#8b949e` | Captions, secondary nav |
| `--green` | `#3fb950` | Primary action, prompt, keys, done or live |
| `--green-hi` to `--teal` | `#56d364` to `#39c5cf` | Wordmark gradient only |
| `--blue` | `#58a6ff` | Links and focus ring |
| `--amber` | `#d29922` | In progress, next |
| `--red` | `#f85149` | Window close dot, failures in evidence copy |

Rules:
- Green means done or live. Amber means in progress. Never swap them for decoration.
- The gradient belongs to the ASH wordmark and nowhere else. No gradient text, no glow.
- Contrast: body text 12:1, muted text 6:1, button label on green 7:1.

## Typography

One superfamily, self-hosted as variable WOFF2 (SIL OFL): the Red Hat typefaces, chosen because the brand prompt is `ash@fedora`.

| Role | Face | Size | Weight | Notes |
|---|---|---|---|---|
| Statement (h1) | Red Hat Display | clamp 2.35rem to 4.5rem | 700 | line-height 1.03, tracking -0.032em |
| Section (h2) | Red Hat Display | clamp 1.75rem to 2.5rem | 700 | tracking -0.025em |
| Claim (h3) | Red Hat Display | 1.375rem | 600 | |
| Body | Red Hat Text | 1.0625rem | 400 | line-height 1.62, measure 52 to 62ch |
| Lead | Red Hat Text | 1.1875rem | 400 | |
| Terminal | Red Hat Mono | 0.875 to 0.9375rem | 400 and 700 | prompts, commands, key and value rows |

Rules:
- No eyebrow labels above headings. No all-caps labels.
- Headings use `text-wrap: balance`, body uses `text-wrap: pretty`.
- Fallback stacks: Segoe UI and system-ui for sans, DejaVu Sans Mono, Menlo and Consolas for mono.

## Layout

- Content width 73.75rem, side gutter 1.25rem minimum.
- Left aligned throughout. Nothing is centered.
- Spacing scale on a 4px base: 4, 8, 12, 16, 24, 32, 48, 72, 112.
- Breakpoints: 56rem (hero and ledger stack to one column), 34rem (phone: terminal rows stack, nav shows section links only).
- More space above a heading than below it. Sections are separated by a 1px rule, not by background bands.

## Elevation and Shapes

- Flat. Elevation is a 1px `--line` border only. No shadows.
- Radius: 10px on terminal windows, 6px on buttons and evidence images, 4px on command chips. No pills.

## Components

- **Wordmark.** ASH drawn as pixel blocks in inline SVG with the green to teal gradient. Used in the header, the favicon (letter A) and the closing section.
- **Terminal window.** Title bar on `--surface` with a centered muted title and three dots at the right (two slate, one red). Body on `--bg`. One prompt line, then output. Used once per section at most.
- **fastfetch block.** Photo in the logo slot, then `ash@Ash5457`, a short rule, key and value rows (keys green and bold), and the 8 colour swatch strip.
- **Case file ledger.** One row per claim: step number (only where the steps are a real sequence), the claim as a heading, one or two sentences, an optional command chip, and the proof image at the right linking to the full screenshot on GitHub.
- **Primary button.** Green fill, dark label, 6px radius. One per screen.
- **Links.** Blue, 1px underline that thickens on hover.

## Motion

One authored moment: on load, `fastfetch` types itself and the output prints row by row, as in the GitHub header. CSS only, about 1.6 seconds, and only when `prefers-reduced-motion` allows it. Everything is visible at rest and without JavaScript. No scroll-triggered fades.

## Do and Don't

Do:
- Put the proof next to the claim.
- Crop evidence screenshots to the relevant window and link to the untouched original.
- Keep every number and date traceable to a repo, a certificate or the resume.

Don't:
- Use mono for body copy.
- Add cards, shadows, glow or glass.
- Add a fake interactive shell.
- State a qualification, employer, metric or tool experience the source material does not support.
