# Atelier Academy

A private, structured course of study for an advanced, arts-focused student: a fixed daily timetable of about six hours, placement diagnostics, a full-year scope and sequence, complete lessons with exercises and separate answer keys, and progress tracking stored only in the browser. The language of instruction is English. Latin and Spanish are taught as daily subjects.

**Privacy:** the site contains no personal information, uses no accounts, analytics, cookies, fonts or scripts from other servers, and asks search engines not to index it (`noindex`). Progress checkmarks live only in the browser's localStorage.

## What is in it

| Page | Purpose |
|---|---|
| Today | Shows the lessons for the current school day, counted from a term start date you set |
| Timetable | The weekly schedule and minutes per subject |
| Placement | Diagnostics in every subject, with an answer key that routes each result |
| Scope & sequence | The 36-week year, term by term, for every subject |
| Lessons | Weeks 1–2 complete: 10 days, 80 lessons, each with exercises and a separate key |
| Electives, Progress, Methods, Sources | As named |

## Method choices, and why

| Subject | Method | Why |
|---|---|---|
| Mathematics | Singapore bar models for modeling; Kiselev's geometry with proof; Gelfand-style algebra; Russian problem-book practice | Bar models expose the structure of a problem before algebra; Kiselev builds geometry as proof; Gelfand teaches algebra as understanding; graded problem sets build fluency |
| Writing | The Writing Revolution (sentence-level first); Renaissance *imitatio* and Erasmus's *copia*; Franklin's reconstruction method; the Trivium | Explicit sentence instruction, then imitation of masters, then argument and rhetoric, in that order |
| Atelier | Bargue–Gérôme plates, sight-size, value, cast drawing, then paint and color | The classical academic sequence: one difficulty at a time, accuracy before speed; the largest daily block |
| Physics | Mazur's Peer Instruction with ConcepTests (adapted for one student) | Strong published evidence of conceptual gains |
| Science | Finnish phenomenon-based modules plus Russian olympiad-style problems | Real phenomena that cross subjects, with quantitative rigour |
| Latin | Ørberg's *Lingua Latina per se Illustrata* (natural method), daily | Reading Latin as Latin from the first page |
| History / Literature | Chronological history from primary sources; great books read whole | Judgement grows from reading evidence and whole works |
| Seminar | Logic, music theory, art history, economics and personal finance, electives | Steady weekly exposure to the rest of a liberal education |

The full rationale is on the site's Methods page (`content/pages/methods.md`); every source is in [SOURCES.md](SOURCES.md).

## Status

- **Complete:** placement diagnostics and key; weekly timetable; scope and sequence for the full year; weeks 1–2 of lessons and keys in all subjects; electives list; progress tracking.
- **Planned:** weeks 3–36 in the same format; the alternative modern languages (Italian, French); the remedial and accelerated modules named in the placement routing.

## Building

The site is plain HTML, CSS and JavaScript, generated from Markdown in `content/`:

```
pip install -r requirements.txt
python3 build.py         # writes docs/
python3 check_links.py   # verifies every internal link and anchor
```

`docs/` is committed, so it can be served directly (for example by GitHub Pages from the `docs/` folder, or by opening `docs/index.html` locally).

## Content format

`content/days/dNN.md` holds one school day: a `# Title`, then one `## Lesson name {#id}` section per lesson. Anything after a `### Answer key` heading inside a section is moved to that day's separate key page.
