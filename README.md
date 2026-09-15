# French Study Diary (Template)

A self-contained, single-file language study tool. No build step, no backend, no dependencies — open `index.html` in any browser and start logging.

This is a blank template: the categories are pre-filled as examples, but there's no vocabulary in it yet. Fill it in as you go.

## Features

- **Practice Log** — a day-by-day view of what you've studied. Click any date to expand it and see that day's words and background notes. Tracks days practiced and days since you started, so your streak is visible at a glance.
- **Quiz** — a staged, spaced-repetition-style quiz. New words start as multiple choice; get one right and it graduates to typing; get it right 3 times in a row while typing and it's marked "Mastered." Miss a word at any stage and it resurfaces sooner. A weighted-priority algorithm decides which word to ask next, favoring weak spots over words you've already got down.
- **Words** — every word and phrase you've logged, grouped by subject, with the target language, pronunciation, and English side by side. Exportable as CSV or copyable as plain text.
- **Background** — a place for the etymology, grammar, and history questions that come up along the way, grouped by theme rather than by day.

## How it works

Everything lives in a single HTML file — plain HTML, CSS, and vanilla JavaScript, no frameworks or external libraries. All data lives directly in the script as in-memory JS arrays (`entries` for vocabulary, `notesEntries` for background notes, `dayTitles` for labeling days). There's no database and no login, which also means it has no built-in persistence — changes made through the in-browser form don't survive a page reload. Treat the HTML file itself as the source of truth: edit the arrays directly (or use the CSV export as a backup) as you add new material.

## Customizing

- `CATEGORY_ORDER` and `TOPIC_ORDER` (near the top of the `<script>` block) control which subjects/themes exist and the order they display in. Add, remove, or rename freely.
- Add new vocabulary by pushing an object onto `entries`: `{ date, cat, fr, pron, en }` (rename `fr` if you're studying a language other than French).
- Add background notes by pushing onto `notesEntries`: `{ date, topic, q, a }`.
- `dayTitles` maps an ISO date to a short label shown in the Practice Log.

## Running it

Just open `index.html` in a browser, or visit the GitHub Pages link for this repo if it's enabled (Settings → Pages → Deploy from branch → main → / root).

## Why

Built as a personal language-learning hobby tool, then generalized into a template anyone can adapt for their own language study.
