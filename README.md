# Scout Programme

A 4-year, 12-term continuous cyclical programme plan for a UK Scout Troop (ages 10–14), built around an inclusive, attendance- and participation-based approach. Scouts achieve their core badge requirements during regular weekly meetings; optional weekend camps, night hikes, and paddleboarding sessions provide opportunity-based staged progression on top of that.

## Structure

- `data/terms.yaml` — the 12-term timeline: theme, core goals, badges earned through in-meeting participation, and optional staged-progression opportunities for each term. This is the source of truth for the programme schedule.
- `data/awards.yaml` — the full award catalogue: the top award, the nine challenge awards, the activity badges, and the staged activity badges, each cross-referenced to the term(s) they're earned in.
- `docs/timeline.md` — human-readable rendering of the term-by-term timeline.
- `docs/awards-summary.md` — human-readable rendering of the award catalogue.
- `year-<N>/term-<N>/overview.md` — itemised, session-by-session breakdown for a given term (indexes one file per weekly meeting), added as terms get planned in detail. See `year-1/term-1/overview.md` for the first example.
- `year-<N>/term-<N>/<session-name>.md` — full delivery plan for a single weekly meeting: a 2-hour running order, how it fits the term's theme, which badge requirement (if any) it targets, and facilitation detail for each activity. Named for what's delivered (e.g. `tent-pitching-outdoor-practical.md`), not numbered, since the order lives in that term's `overview.md`.
- `welcome-session.md` — every term's opening session, always the same shape (welcome, icebreaker, Scouts agree their own rules for the term, then Scout-chosen games) and deliberately generic so it can be copied into any future term's opening slot with only the term name changed.

The `docs/*.md` files are rendered views of the `data/*.yaml` files. When changing the programme, edit the YAML first and update the corresponding doc to match.

## Source

Converted from the original planning document: [UK Scout 4-Year Program Plan](https://docs.google.com/document/d/1dEWD9er0wP04b8CBeQ2GrCP8pQHZMMAqY8jL9BzbvQ4/edit).
