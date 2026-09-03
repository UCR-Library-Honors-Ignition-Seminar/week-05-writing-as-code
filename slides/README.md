# Week 5 Slides — Writing as Code / Code as Writing

Quarto `revealjs` decks for the two 90-minute honors seminar sessions.

## Files

| File | What it is |
|---|---|
| `_quarto.yml` | Shared format / author block for both decks |
| `assets/slides.scss` | UCR-brand reveal.js theme (blue `#003da5` / gold `#ffb81c`), copied from the *computational-approaches-text-analysis* deck |
| `logo.png` | UC Riverside Library logo, shown bottom-right on every slide |
| `session-1-twine.qmd` | Session 1 — Branching Stories with Twine |
| `session-2-tracery.qmd` | Session 2 — Text That Writes Itself: Tracery |
| `_output/` | Rendered HTML (git-ignored candidate) |

## Style

Matches `github.com/jinghanlib/computational-approaches-text-analysis`:
gold h1 / blue underlined h2, blue `#` section dividers, **gold background** on
hands-on exercise slides, `.callout-box` (blue) and `.gold-box` accent boxes,
chalkboard enabled (`B` key), progress bar, UCR Library logo + footer.

## Preview / edit

```bash
quarto preview session-1-twine.qmd   # live-reload in browser
quarto render                        # build both to _output/
```

Speaker view: press `S` in the browser. Full screen: `F`. Overview: `O`.

## Presenting notes

- `. . .` = a fragment break (click to advance within a slide)
- `#` headings become section-divider slides
- Session activity timings are on the "Today" slide and each `# Experience first` divider

## Adding to the course repo — options (not yet done)

1. **`slides/` subfolder in the existing repo** — drop these three files under
   `week-05-writing-as-code/slides/`, link the rendered decks from `README.md`.
2. **GitHub Pages** — the repo already has `.github/workflows/`; add a
   `quarto-actions/render` + `publish` step (or `quarto publish gh-pages` locally)
   to serve the decks at a public URL.
3. **Keep separate** — leave this folder outside the repo, hand out PDF exports
   (`quarto render session-1-twine.qmd --to pdf`, needs a Chromium install).
