# Design notes

A dark, left-aligned site that borrows from the terminal header on my GitHub profile. Body text is a sans face. Monospace is only used where a terminal would print the text: prompts, commands, file paths and the key and value rows.

The home page is short: who I am, three project previews, and my background. Each project has its own page.

## Colours

Taken from `scripts/build_header.py` in the profile repo. Dark only on screen.

| Token | HEX | Use |
|---|---|---|
| `--bg` | `#0d1117` | Page and terminal body |
| `--surface` | `#161b22` | Terminal title bar, command chips, image caption bar |
| `--line` | `#30363d` | Every border and rule, 1px |
| `--strong` | `#f0f6fc` | Headings |
| `--text` | `#c9d1d9` | Body text |
| `--muted` | `#8b949e` | Captions, dates, labels |
| `--green` | `#3fb950` | Main button, prompt, keys, finished |
| `--green-hi` to `--teal` | `#56d364` to `#39c5cf` | ASH wordmark gradient only |
| `--blue` | `#58a6ff` | Links and focus ring |
| `--amber` | `#d29922` | In progress, next |
| `--red` | `#f85149` | Window close dot |

Green means finished or live and amber means in progress. The gradient is only for the wordmark.

## Type

Red Hat Display for headings, Red Hat Text for body, Red Hat Mono for terminal text. All three are self-hosted variable fonts.

- Home headline: clamp 2.35rem to 4.5rem, weight 700
- Project page title: clamp 2.1rem to 3.5rem, weight 700
- Section headings: clamp 1.6rem to 2.25rem
- Body: 1.0625rem, line-height 1.62, lines kept under about 64 characters

## Layout

- Content width 73.75rem, side gutter at least 1.25rem.
- Everything is left aligned.
- Breakpoints: 56rem (two-column layouts stack), 40rem (header drops the name and the Background link), 34rem (phone).
- Flat. Borders are 1px, there are no shadows. Radius is 10px on terminal windows and cards, 6px on buttons and images.

## Parts

- **Header.** Sticky, solid background. Wordmark, section links, then Email, GitHub and LinkedIn so contact is always in view.
- **Terminal window.** Title bar with three dots, one prompt line, then output. Used for the fastfetch summary on the home page and one summary per project page.
- **Project card.** A small terminal window holding the project's diagram, with the status, title, two or three sentences and the tools underneath. The whole card links to the project page.
- **Proof row.** A claim on the left and the screenshot on the right. Under the image is a bar with the file's path in the repo and a "View on GitHub" button. Rows from a real sequence are labelled, for example "Step 4 of 12".
- **What went wrong.** A heading, then what I saw, the cause and the fix.

## Motion

One animation: on the home page `fastfetch` types itself and the output prints. It is CSS only and is skipped when the visitor has reduced motion turned on.

## Writing

First person, plain, and specific. If a sentence only sounds good, it gets cut. Every number and date has to match the repos or my resume.
