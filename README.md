# Scout Programme

A 4-year, 12-term continuous cyclical programme plan for a UK Scout Troop (ages 10–14), built around an inclusive, attendance- and participation-based approach. Scouts achieve their core badge requirements during regular weekly meetings; optional weekend camps, night hikes, and paddleboarding sessions provide opportunity-based staged progression on top of that.

## Structure

- `data/terms.yaml` — the 12-term timeline: theme, core goals, badges earned through in-meeting participation, and optional staged-progression opportunities for each term. This is the source of truth for the programme schedule.
- `data/awards.yaml` — the full award catalogue: the top award, the nine challenge awards, the activity badges, and the staged activity badges, each cross-referenced to the term(s) they're earned in.
- `docs/timeline.md` — human-readable rendering of the term-by-term timeline.
- `docs/awards-summary.md` — human-readable rendering of the award catalogue.
- `year-<N>/term-<N>/overview.md` — itemised, session-by-session breakdown for a given term (indexes one file per weekly meeting), added as terms get planned in detail. See `year-1/term-1/overview.md` for the first example.
- `year-<N>/term-<N>/<session-name>.md` — full delivery plan for a single weekly meeting: a 2-hour running order, how it fits the term's theme, which badge requirement (if any) it targets, and facilitation detail for each activity. Named for what's delivered (e.g. `tent-pitching.md`), not numbered, since the order lives in that term's `overview.md`.
- `welcome-session.md` — every term's opening session, always the same shape (welcome, icebreaker, Scouts agree their own rules for the term, then Scout-chosen games) and deliberately generic so it can be copied into any future term's opening slot with only the term name changed.
- `end-of-term-fun-and-games.md` — every term's closing session: a short badge presentation, then Taskmaster-style challenges. Same reuse convention as `welcome-session.md`.
- `night-hike.md`, `camp.md` — two more fixed slots every term includes, each replacing that week's normal hall meeting and following a different running-order shape (multi-hour or multi-day) than the standard 2-hour template. Content is term-specific (what the hike/camp actually involves), tying into that term's badge work.
- `external-activity.md` — the fifth fixed slot: a booked, purely-for-fun outing (paddleboarding, a hired climbing wall, volleyball courts, and so on) that's deliberately unrelated to the term's theme or badge work. A placeholder until the term's actual activity is booked.

Every term's 12 weeks therefore break down as: 1 Welcome Session + 1 Night Hike + 1 Camp + 1 External Activity + 1 End of Term Fun & Games (five fixed slots, same shape every term) + 7 weeks of the term's own badge content.

The `docs/*.md` files are rendered views of the `data/*.yaml` files. When changing the programme, edit the YAML first and update the corresponding doc to match.

## Status

`year-1/term-1/` is the first term planned in full session-level detail, and the template for how every other term should eventually look. The other 11 terms currently exist only at the summary level in `data/terms.yaml` (theme, core goals, badges, staged progression) — no `year-<N>/term-<N>/` directory yet.

**Keep `data/*.yaml` and `docs/*.md` in sync with the session-level detail at all times.** When a term's session files change in a way that affects what's actually earned or covered that term — a badge gets fully covered, a requirement moves to a different term, staged progression changes — update `data/terms.yaml` and `data/awards.yaml` (and the corresponding `docs/*.md` rendering) in the same piece of work, not as a follow-up. The summary-level files should always describe what the detailed session plans actually do, never what they used to do.

## Source

Converted from the original planning document: [UK Scout 4-Year Program Plan](https://docs.google.com/document/d/1dEWD9er0wP04b8CBeQ2GrCP8pQHZMMAqY8jL9BzbvQ4/edit).
