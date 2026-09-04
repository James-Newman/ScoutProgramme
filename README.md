# Scout Programme

A 4-year, 12-term continuous cyclical programme plan for a UK Scout Troop (ages 10–14), built around an inclusive, attendance- and participation-based approach. Scouts achieve their core badge requirements during regular weekly meetings; optional weekend camps, night hikes, and paddleboarding sessions provide opportunity-based staged progression on top of that.

## Structure

- `data/terms.yaml` — the 12-term timeline: theme, core goals, badges earned through in-meeting participation, and optional staged-progression opportunities for each term. This is the source of truth for the programme schedule.
- `data/awards.yaml` — the full award catalogue: the top award, the nine challenge awards, the activity badges, and the staged activity badges, each cross-referenced to the term(s) they're earned in.
- `docs/timeline.md` — human-readable rendering of the term-by-term timeline.
- `docs/awards-summary.md` — human-readable rendering of the award catalogue.
- `year-<N>/term-<N>/overview.md` — itemised, session-by-session breakdown for a given term (indexes one file per weekly meeting) plus a **material inventory**: every additional resource the term's sessions need, consolidated and quantified for the group's maximum of 6 patrols (scale down for a smaller group). Added as terms get planned in detail. See `year-1/term-1/overview.md` for the first example.
- `year-<N>/term-<N>/<session-name>.md` — full delivery plan for a single weekly meeting: a 2-hour running order, how it fits the term's theme, which badge requirement (if any) it targets, and facilitation detail for each activity. Named for what's delivered (e.g. `tent-pitching.md`), not numbered, since the order lives in that term's `overview.md`.
- `welcome-session.md` — every term's opening session, always the same shape (welcome, icebreaker, Scouts agree their own rules for the term, then Scout-chosen games) and deliberately generic so it can be copied into any future term's opening slot with only the term name changed.
- `end-of-term-fun-and-games.md` — every term's closing session: a short badge presentation, then Taskmaster-style challenges. Same reuse convention as `welcome-session.md`.
- `night-hike.md`, `camp.md` — two more fixed slots every term includes, each replacing that week's normal hall meeting and following a different running-order shape (multi-hour or multi-day) than the standard 2-hour template. Content is term-specific (what the hike/camp actually involves), tying into that term's badge work.
- `external-activity.md` — the fifth fixed slot: a booked, purely-for-fun outing (paddleboarding, a hired climbing wall, volleyball courts, and so on) that's deliberately unrelated to the term's theme or badge work. A placeholder until the term's actual activity is booked.

Every term's 12 weeks therefore break down as: 1 Welcome Session + 1 Night Hike + 1 Camp + 1 External Activity + 1 End of Term Fun & Games (five fixed slots, same shape every term) + 7 weeks of the term's own badge content.

- `resources/` — printable materials (cards, templates, checklists, posters) referenced from `year-1/term-1/`'s material inventory that don't already exist as an official download. See `resources/README.md` for the index and for the real official downloads used instead of a local copy.
- `filler-sessions/` — standalone sessions for when a term runs longer than planned: each completes a full, real Scout Activity Badge in one sitting, with no term theme and no dependency on any other session. See `filler-sessions/README.md`.

The `docs/*.md` files are rendered views of the `data/*.yaml` files. When changing the programme, edit the YAML first and update the corresponding doc to match.

## Status

`year-1/term-1/` (World Challenge Award) and `year-1/term-2/` (Outdoor Challenge Award content) are the two terms planned in full session-level detail so far. The other 10 terms currently exist only at the summary level in `data/terms.yaml` (theme, core goals, badges, staged progression) — no `year-<N>/term-<N>/` directory yet.

Two things are deliberately unresolved right now, flagged in `data/terms.yaml`:
- Year 1, Term 2's original content ("Global Citizens & Conservation") was displaced when the World Challenge Award moved into Term 1 and the outdoor content moved into Term 2, and hasn't been re-slotted anywhere yet.
- The group is moving away from treating the Outdoor Challenge Award as a dedicated focus-badge term at all — the intent is to earn it passively through the standing Camp/Night Hike slots every term already has, rather than a dedicated term of tent-pitching/site-layout/fire-safety sessions. `year-1/term-2/`'s content is held as-is for now pending that redesign.

**Keep `data/*.yaml` and `docs/*.md` in sync with the session-level detail at all times.** When a term's session files change in a way that affects what's actually earned or covered that term — a badge gets fully covered, a requirement moves to a different term, staged progression changes — update `data/terms.yaml` and `data/awards.yaml` (and the corresponding `docs/*.md` rendering) in the same piece of work, not as a follow-up. The summary-level files should always describe what the detailed session plans actually do, never what they used to do.

## Passive badge completion

Every term focuses on completing one badge in full within that term — but a term's regular content (games, camps, hikes, teamwork/leadership activities) sometimes also advances real requirements of *other* Scouts-section badges, without any dedicated session time for them. When a term is built out, check whether its sessions incidentally touch other badges (prioritise obvious thematic overlaps — don't exhaustively research every Scouts-section badge), and document any genuine overlap as a **Passive completion** section in that term's `overview.md`, being explicit about whether it's a full or only partial match against the real requirement wording. See `year-1/term-1/overview.md` for the first example (Environmental Conservation Activity Badge and International Activity Badge, both partial).

## Source

Converted from the original planning document: [UK Scout 4-Year Program Plan](https://docs.google.com/document/d/1dEWD9er0wP04b8CBeQ2GrCP8pQHZMMAqY8jL9BzbvQ4/edit).
