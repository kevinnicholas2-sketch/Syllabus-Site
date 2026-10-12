# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

A single-page course syllabus website. Plain HTML + CSS only: no JavaScript, no build step, no package manager, no tests, no linter. It is a git repository on branch `main`, so commit before any large redesign. `git` is not on the PATH on this machine; the copy bundled with GitHub Desktop works (`C:\Users\kevin\AppData\Local\GitHubDesktop\app-<version>\resources\app\git\cmd\git.exe`, version folder changes on app updates).

## Layout

- `index.html` — the entire page.
- `styles.css` — all styling, including the `@media print` block.
- `README.md` — public-facing overview: sections, how to view and edit each term, design notes, and the list of placeholders still to fill. Keep it in sync when sections, files, or placeholders change.
- `claude-mobile.png` — hero cover image (halftone statue with code-reflecting glasses), from an Every (every.to) post cover. Shown in a gold frame under the title (`figure.cover`), hidden in print. Kevin supplied it; he is responsible for usage rights.

(Update this section when files are added.)

## Running / previewing

No build. Open `index.html` directly in a browser, or serve the folder statically
(e.g. `python -m http.server 8765` from this folder). If using `.claude/launch.json`,
point it at a static server that lives in the project, not at temp/scratchpad paths.

## Page structure

One `<header>` and a `<main>` with one `<section>` per topic, in this order, each with an `id` so a top nav can anchor to it:

1. **Course Info** (`#info`) — title, course code, term, meeting days/time/location, instructor name, email, office hours, course description and learning objectives.
2. **Weekly Schedule** (`#schedule`) — 14-week table of topics and due dates/assessments. Week numbers only, no calendar dates yet (the term dates are unknown); add a Date column once they are.
3. **Grading** (`#grading`) — assignment/assessment list with weights (a table), and the grading scale.
4. **Policies** (`#policies`) — attendance, late work, academic integrity, accessibility/accommodations.

Section numbers in the headings come from a CSS counter, so adding or reordering sections renumbers them automatically. When adding a section, also add its link to the top nav. Keep the schedule consistent with the grading table (the quizzes, assignments, midterm, and final project it lists should match).

## Conventions

- **Theme lives in CSS custom properties in `:root`** (colors, fonts, spacing). Change values there, not per-rule.
- **Visual style is classic Ivy League academic:** white page, crimson accent (`--crimson`), serif body and display fonts with small-caps sans labels (`--label`), hairline rules instead of boxes or fills, centered masthead, and CSS-counter-numbered section headings (`h2::before`). Style only: do not use any university's name, shield, or logo.
- **Course content is hard-coded in HTML.** Keep all course-specific text (code, term, instructor, dates, weights) in `index.html` so it is the single place to edit between terms.
- **Grade weights must add up to 100%.** When editing the grading table, re-check the total.
- Use semantic elements (`header`, `nav`, `main`, `section`, `table` with `<caption>` and `<th scope>`), one `<h1>`, and heading levels that never skip.
- Use `<table>` for the grading breakdown and grading scale, not divs.
- Prefer system font stacks; if web fonts are added, keep system fallbacks in the font variable.

## Accessibility

- Text/background contrast at least WCAG AA (4.5:1 body text).
- Visible focus styles on links and any interactive element; add a "Skip to content" link.
- Decorative elements get `aria-hidden="true"`.
- Include a `prefers-reduced-motion` block that disables smooth scroll and transitions.
- Set `<html lang="en">` and a viewport meta tag.

## Print

Students print syllabi, so keep a `@media print` block in `styles.css`: hide the nav, use black text on white, avoid page breaks inside table rows and headings (`break-inside: avoid`), and show link URLs where useful. Check print preview after layout changes.

## Responsive

One breakpoint (around `max-width: 800px`); the page must be readable on a phone. Tables should not overflow the viewport (wrap in a scrollable container or restack).

## Known open items

- Course is "Claude Coding Bootcamp", held at Noble Desktop, Fall term (no year given). Kevin asked to remove the Baruch College name, Room 212, and the course code; don't re-add them. The masthead is a glitzy midnight `.hero` (gold shimmer `h1`, twinkling `.sparkle` spans, gold rules) over the otherwise classic page; print and reduced-motion blocks flatten it. The Learning Objectives list is intentionally empty (a `.todo` placeholder line); Kevin will supply the goals.
- All four instructor fields (name, email, office, office hours) are intentionally `TBD` at Kevin's request; fill them in when known.
- The weekly schedule topics are drafted Claude-coding topics (Claude Code, CLAUDE.md, MCP, subagents/skills/hooks, API/Agent SDK) and the due items are placeholders (3 assignments, 3 quizzes, midterm in week 8, final project in week 14); confirm with Kevin.
- Class meets Mon & Wed starting 10:00 AM (end time not yet given).
- The grading table descriptions are filled in (drafted by Claude to match the schedule: 3 quizzes, 3 assignments, midterm week 8, final project with proposal week 11 and presentation week 14). The weights (10/15/25/20/30) are the original placeholders, so confirm them with Kevin.
- Class end time, course description, and policy text are still placeholders until Kevin supplies them.
