# Scout Programme

A 3-year, 9-term continuous cyclical programme plan for a UK Scout Troop (ages 10–14), built around an inclusive, attendance- and participation-based approach. Scouts achieve their core badge requirements during regular weekly meetings; optional weekend camps, night hikes, and paddleboarding sessions provide opportunity-based staged progression on top of that.

## Structure

- `data/terms.yaml` — the 9-term timeline: theme, core goals, badges earned through in-meeting participation, and optional staged-progression opportunities for each term. This is the source of truth for the programme schedule.
- `data/awards.yaml` — the full award catalogue: the top award, the ten challenge awards, the activity badges, and the staged activity badges, each cross-referenced to the term(s) they're earned in.
- `docs/timeline.md` — human-readable rendering of the term-by-term timeline.
- `docs/awards-summary.md` — human-readable rendering of the award catalogue.
- `year-<N>/term-<N>/overview.md` — itemised, session-by-session breakdown for a given term (indexes one file per weekly meeting) plus a **material inventory**: every additional resource the term's sessions need, consolidated and quantified for the group's maximum of 6 patrols (scale down for a smaller group). Added as terms get planned in detail. See `year-1/term-1/overview.md` for the first example.
- `year-<N>/term-<N>/<session-name>.md` — full delivery plan for a single weekly meeting: a 2-hour running order, how it fits the term's theme, which badge requirement (if any) it targets, and facilitation detail for each activity. Named for what's delivered (e.g. `tent-pitching.md`), not numbered, since the order lives in that term's `overview.md`.
- `welcome-session.md` — every term's opening session, always the same shape (welcome, icebreaker, Scouts agree their own rules for the term, then Scout-chosen games) and deliberately generic so it can be copied into any future term's opening slot with only the term name changed. The "agree own rules" block doubles as a Patrol/Troop Forum towards the Teamwork Challenge Award, and the icebreaker should vary term to term to count as a new team-building activity.
- `end-of-term-fun-and-games.md` — every term's closing session: a short badge presentation, then Taskmaster-style challenges. Same reuse convention as `welcome-session.md`.
- `night-hike.md` — a fixed slot every term includes, replacing that week's normal hall meeting, with its own running-order shape (an evening/night event, not the standard 2-hour template). Content is term-specific, but every Night Hike should also touch on the Countryside Code, which is the standing home for that Outdoor Challenge Award requirement.
- `camp.md` — another fixed slot every term includes, a multi-day running order (typically Friday evening–Sunday). Every Camp should include a site walk on arrival and a leave-no-trace check before departure — the standing home for two more Outdoor Challenge Award requirements (Nights Away, and exploring/respecting the environment).
- `external-activity.md` — a booked, purely-for-fun outing (paddleboarding, a hired climbing wall, volleyball courts, and so on) that's deliberately unrelated to the term's theme or badge work. A placeholder until the term's actual activity is booked. Whatever gets booked also counts towards the Adventure Challenge Award's "four different adventurous activities" tally.
- `little-o-orienteering.md` — a sixth fixed slot, **Autumn terms only**: a short orienteering session in the local park. Currently a placeholder — see the file itself.

Every term's 12 weeks therefore break down as: 1 Welcome Session + 1 Night Hike + 1 Camp + 1 External Activity + 1 End of Term Fun & Games (five fixed slots every term, a sixth — Little O — in Autumn terms only) + the term's own badge content in the weeks left over (6 in Autumn, 7 in Spring/Summer).

- `resources/` — printable materials (cards, templates, checklists, posters) referenced from a term's material inventory that don't already exist as an official download. See `resources/README.md` for the index and for the real official downloads used instead of a local copy.
- `filler-sessions/` — standalone sessions sitting outside the 9-term plan, of two kinds: complete-in-one-sitting badges (each finishes a full, real Scout Activity Badge in a single sitting) and passive-progress badges (`outdoor-challenge-award/`, `adventure-challenge-award.md`, `teamwork-challenge-award.md` — badges the group decided to never dedicate a whole term to, earned instead across many terms via the standing fixed slots above plus these sessions). See `filler-sessions/README.md`.

The `docs/*.md` files are rendered views of the `data/*.yaml` files. When changing the programme, edit the YAML first and update the corresponding doc to match.

## Status

`year-1/term-1/` (World Challenge Award), `year-1/term-2/` (Emergency Aid Staged Activity Badge, Stage 3), `year-1/term-3/` (Chef Activity Badge), `year-2/term-1/` (Creative Challenge Award), `year-2/term-2/` (Pioneer Activity Badge), and `year-2/term-3/` (Paddle Sports Staged Activity Badge, Stage 1) are the terms started so far — Year 1, Term 1 in full session-level detail, all the others at framework level only (theme and badges in `data/terms.yaml` plus a placeholder `overview.md`; session-by-session detail is still to come). The other 3 terms (all of Year 3) exist only at the summary level in `data/terms.yaml` — no `year-<N>/term-<N>/` directory yet.

Outdoor Challenge Award, Adventure Challenge Award, and Teamwork Challenge Award are **never** a dedicated focus-badge term — earned passively instead, per `filler-sessions/`'s passive-progress badges and the standing fixed-slot guidance above. This was a deliberate group decision, not something left open to reconsider.

The programme was originally a 4-year, 12-term plan. It has since moved to 3 years, 9 terms: Year 4 was dropped entirely (it had never been built out beyond the summary level, so there was no session content to migrate), and its badges — Survival Skills Activity Badge, Photographer Activity Badge, Campers Activity Badge, and Cycle 2 refreshers of the Global Issues and Expedition Challenge Awards — are dropped from the programme, not re-slotted. The Chief Scout's Gold Award (the top award) is no longer tied to a specific term either; it's presented to each Scout individually as they complete the requirements, whenever that happens to fall. See `data/terms.yaml` and `data/awards.yaml`.

Several things are still flagged unresolved in `data/terms.yaml`: Year 1, Term 2's original content ("Global Citizens & Conservation," before it briefly became Outdoor Challenge Award content) hasn't been re-slotted anywhere; and Year 2's original content (Team Leader Challenge Award, Navigator Staged Activity Badge Stage 3/4, Scientist/Artist Activity Badge, Expedition Challenge Award, Hiker Activity Badge), displaced when Year 2's three terms were rebuilt around Creative Challenge/Pioneer/Paddle Sports, hasn't been re-slotted anywhere either.

**Keep `data/*.yaml` and `docs/*.md` in sync with the session-level detail at all times.** When a term's session files change in a way that affects what's actually earned or covered that term — a badge gets fully covered, a requirement moves to a different term, staged progression changes — update `data/terms.yaml` and `data/awards.yaml` (and the corresponding `docs/*.md` rendering) in the same piece of work, not as a follow-up. The summary-level files should always describe what the detailed session plans actually do, never what they used to do.

## Passive badge completion

Two distinct things go by this name:

1. **Deliberate design** — Outdoor Challenge Award, Adventure Challenge Award, and Teamwork Challenge Award are never given a dedicated term; they're earned entirely through the standing fixed slots and the passive-progress sessions in `filler-sessions/`.
2. **Incidental overlap** — separately, a term's regular content sometimes advances real requirements of *other* Scouts-section badges without any dedicated session time for them. When a term is built out, check whether its sessions incidentally touch other badges (prioritise obvious thematic overlaps — don't exhaustively research every Scouts-section badge), and document any genuine overlap as a **Passive completion** section in that term's `overview.md`, being explicit about whether it's a full or only partial match against the real requirement wording. See `year-1/term-1/overview.md` for the first example (Environmental Conservation Activity Badge and International Activity Badge, both partial).

Either way: a badge only counts as "earned" in `data/awards.yaml` once every one of its requirements is genuinely met — partial progress stays documented in prose, not recorded as complete.

## Source

Converted from the original planning document: [UK Scout 4-Year Program Plan](https://docs.google.com/document/d/1dEWD9er0wP04b8CBeQ2GrCP8pQHZMMAqY8jL9BzbvQ4/edit).
