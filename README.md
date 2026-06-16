# bayesian-statistics

Public-facing Quarto **course-materials site** for an undergraduate
**Bayesian Statistics** course, assembled by Matt Hester. Sibling to the
main site [matthewhester.com](https://matthewhester.com); intended to
live at `/bayesian-statistics/` under that domain.

This is **assembled undergraduate course material** — synthesized
lesson notes, hands-on R/Quarto labs, and curated references. It is a
durable public resource site, **not** a record of a currently scheduled
section, and **not** an LMS.

## Status

Assembled from a course-material build (2026-06). Topic flow, notes,
labs, and resources are in place. Dates, weights, and final policies are
not sealed and are authoritative in the LMS whenever the course runs.
Treat the site as a coherent draft, not a final release.

## What this site holds

- **Notes** — the weekly instructional spine (15 weeks, five parts):
  discrete Bayes, priors/likelihoods/posteriors, Beta-Binomial, prior
  sensitivity, posterior prediction, simulation-first computation,
  Bayesian regression, model checking, and introductory hierarchical
  models.
- **Labs** — four reproducible R + Quarto labs (posterior simulation,
  grid approximation, Bayesian regression, partial pooling).
- **Resources** — software setup, a notation glossary, and a
  Bayes-vs-classical reference.

The primary open text is *Bayes Rules! An Introduction to Applied
Bayesian Modeling* (Johnson, Ott, Dogucu; CC BY-NC-SA 4.0). These notes
are the course's **own synthesis**, attributed at the chapter/section
level — not bulk-copied source text.

## What does not go in this repo

Anything private to a graded offering: answer keys, assessment items,
rubrics, point values, due dates, student data, or any directory from
the private course build (`_state/`, `assessment_shadow/`,
`source_text/`, `run_reports/`, `specs/`, `private_output/`,
`accessibility/`, `export/`). See [`CLAUDE.md`](CLAUDE.md) for the full
list. The operational, graded side of any live offering lives in
**Blackboard (the LMS)**, which is authoritative.

## Local development

```bash
quarto render     # build to _site/
quarto preview    # live preview
```

The weekly notes and labs contain executable `{r}` chunks (figures), so
a full render needs **R + knitr** installed. To validate structure,
links, and images without R:

```bash
quarto render --no-execute   # renders prose + code, skips R execution
```

## Layout

```
bayesian-statistics/
├── _quarto.yml              # site config, navbar, sidebar, render allow-list
├── index.qmd                # landing page (hero + overview)
├── syllabus.qmd             # public course overview
├── schedule.qmd             # week-by-week topic map
├── notes/                   # weekly instructional notes + index
├── labs/                    # reproducible R/Quarto labs + index
├── resources/               # setup, notation glossary, references + index
├── assets/                  # hero.png + icon.png (course identity art)
├── styles.css               # course-family palette
├── CLAUDE.md                # privacy + editing rules
└── README.md                # this file
```

No CI and no deploy pipeline in this repo. The combined site is
assembled and deployed by the hub repo (`matthewhester-site`). Local
builds only here; commits are deliberate and user-driven.
