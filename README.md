# Claude Coding Bootcamp Syllabus

A single-page course syllabus for the Claude Coding Bootcamp, which meets Monday and Wednesday at 10:00 AM at Noble Desktop in the Fall term. The site is plain HTML and CSS, meant to be read on screen or printed for students.

## Sections

1. **Course Info**: meeting time, instructor details, course description, learning objectives.
2. **Weekly Schedule**: a 14-week table of topics and due items.
3. **Grading**: grade component weights and the letter grade scale.
4. **Policies**: attendance, late work, academic integrity, accessibility and accommodations.

## Features

- Plain HTML and CSS only: no JavaScript, no build step, no package manager, no tests.
- Hero masthead with a cover image; the navigation links jump to each section.
- Print styles: hides the navigation and decorative hero elements, uses black on white, avoids page breaks inside table rows and headings, and prints the URL after mailto and http links.
- One responsive breakpoint at 800px. Wide tables scroll horizontally inside their container.
- Accessibility: skip link, visible focus outline, tables with captions and header scope, decorative elements hidden from assistive technology, and a reduced-motion block that disables animations, smooth scrolling and transitions.

## Getting started

Open `index.html` directly in a browser, or serve the folder with any static file server. On machines where `python` is only the Microsoft Store stub (as on the author's Windows machine), `python -m http.server` will not run, so use another server or just open the file.

No installation or environment variables are needed.

## Editing for a new term

All course-specific text is in `index.html`. Placeholders are written in [square brackets] or set to `TBD`.

- **Meeting time**: the Meeting Time card in Course Info.
- **Instructor**: the Instructor card in Course Info.
- **Description and learning objectives**: the paragraphs under Course Info.
- **Schedule**: the rows of the Weekly Schedule table.
- **Grading**: the weights in the Grading table. The Total row is typed text, not calculated, so re-check it. Weights must total 100%. The quizzes and assignments in the schedule's Due column should match the Grading table.
- **Policies**: the four `.policy` blocks.
- **Title and heading**: the `<title>`, the `<h1>`, and the tagline in `index.html`.
- **Cover image**: the `figure.cover` block, which uses `claude-mobile.png`. Its usage rights should be checked before publishing.

Colors and fonts are CSS custom properties in the `:root` block of `styles.css` (for example `--crimson`, `--gold`, `--night`, `--display`, `--body`).

## Design

The page has a white body with a crimson accent, serif display and body type with system font fallbacks (no web fonts are loaded), small uppercase sans-serif labels, and hairline rules instead of boxes. Section headings are numbered automatically with a CSS counter. The masthead is a midnight-and-gold hero with a shimmering title and twinkling sparkles. The print and reduced-motion styles flatten it. The design is style only and carries no university name or logo.

## Placeholders still to fill

- Meeting end time (currently "10:00 AM [end time]").
- Instructor name, email, office, and office hours (all `TBD`).
- Course description.
- Learning objectives.
- Late work policy.
- Academic integrity policy.
- Accessibility and accommodations policy.

The weekly topics and grade weights (10%, 15%, 25%, 20%, 30%) are draft placeholders and should be confirmed.

## Project structure

```
Syllabus Site/
├── index.html          the whole page
├── styles.css          all styling, including print and responsive rules
├── claude-mobile.png   hero cover image
├── CLAUDE.md           guidance for Claude Code
└── README.md
```
