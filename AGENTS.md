# AGENTS.md

Instructions for any AI agent working in this repository.

## What this repo is

A 4-year, 12-term programme plan for a UK Scout Troop (ages 10–14), converted from a
Google Doc into git specifically so it's easier to iterate on with an AI agent. The
plan is inclusive and attendance-based: Scouts earn core badge requirements during
regular weekly meetings, with optional camps/hikes/water sessions layered on top as
staged progression.

See `README.md` for the full directory layout. In short:

- `data/*.yaml` is the source of truth for the 4-year schedule and award catalogue.
- `docs/*.md` are rendered, human-readable views of that YAML.
- `year-<N>/term-<N>/` holds full session-by-session delivery plans for a term, built
  out one term at a time. **`year-1/term-1/` is the only term built out so far** and is
  the reference example for how every other term should eventually look.

## The most important rule: keep data and docs in sync, always

`data/*.yaml` and `docs/*.md` must always describe what the `year-<N>/term-<N>/`
session files actually do — never what they used to do. If a change to a term's
session content affects what's earned, when, or how (a badge gets fully covered, a
requirement moves to a different term, staged progression changes), update
`data/terms.yaml` / `data/awards.yaml` and the matching `docs/*.md` rendering **in the
same piece of work**, not as a follow-up. Before asserting a term is "complete" or
"covers X badge," grep the actual session files rather than trusting memory of past
edits — this repo has already had real bugs (a requirement referenced as happening in
a session that had been deleted) that only surfaced by checking the files directly.

## Every term's 12 weeks follow the same shape

Five fixed slots, same shape every term regardless of theme, plus seven weeks of
term-specific badge content:

1. **Welcome Session** (`welcome-session.md`) — welcome, icebreaker, Scouts agree
   their own rules for the term, Scout-chosen games. Deliberately generic — copy it
   into a new term unchanged apart from the term name in the header.
2. **End of Term Fun & Games** (`end-of-term-fun-and-games.md`) — a short badge
   presentation, then Taskmaster-style challenges. Same reuse convention as Welcome.
3. **Night Hike** (`night-hike.md`) — term-specific content, different running-order
   shape (evening/night event, not the standard 2-hour template).
4. **Camp** (`camp.md`) — term-specific content, multi-day running order (typically
   Friday evening–Sunday), not the standard 2-hour template.
5. **External Activity** (`external-activity.md`) — a booked, purely-for-fun outing
   (paddleboarding, a climbing wall, volleyball, etc.) **deliberately unrelated** to
   the term's theme or badge work. Treat this as a placeholder until a term's actual
   activity is booked — never fill it with theme content.

Night Hike, Camp, and External Activity each replace that week's normal hall meeting
rather than sitting alongside it, so the term still totals 12 weeks.

## Session file conventions

- **Name files for what's delivered**, not numbered (`tent-pitching.md`, not
  `session-03.md`) — the sequence lives in that term's `overview.md`, not in
  filenames.
- **Header format**: `Term:`, `Fits the term because:`, `Badge focus:` each as their
  own paragraph (blank line between them) so they render as distinct lines, not one
  run-together block.
- **Quote badge requirements verbatim**, in a blockquote, sourced from the live
  `scouts.org.uk` award/badge page — don't paraphrase. Note that requirement wording
  can be updated by the Scout Association, so re-check the live page before treating
  an old quote as current.
- **Cross-reference other sessions by name and link** (`[Tent Pitching](tent-pitching.md)`),
  never by position ("last week's session", "session 4") — session order can and does
  change.
- **Standard 2-hour sessions**: 10 min welcome + 100 min core content + 10 min close.
  Multi-hour/multi-day sessions (Camp, Night Hike, External Activity) use their own
  shape — say so explicitly rather than forcing the standard template.
- **Leaders are not performers.** Don't design activities that need a leader to act,
  role-play, or run a skit — use card sorts, discussions, quizzes, and games where the
  *Scouts* do the performing. This was an explicit correction from the group: leaders
  running this troop are not "the roleplay, skit, acting type."
- **Minimise leader prep burden.** Prefer activities using what's already in a normal
  Scout store cupboard over bespoke crafted props (a "term trail poster" was removed
  for exactly this reason — reduce extra effort, not add it).
- **Verify links resolve and YAML parses** after any edit — grep for markdown links
  against the filesystem, and validate YAML (e.g. `ruby -ryaml -e '...'` or a Python
  yaml loader) before committing.

## Badge-accuracy discipline

This programme deliberately grounds its fictional term themes in **real** UK Scout
Association badge requirements and real activities from `scouts.org.uk/activities`.
When adding or changing badge-related content:

- Fetch the actual current requirement wording rather than recalling it from
  training data — badge requirements get revised, and this repo has already found
  and corrected stale assumptions (e.g. a badge that was quietly retired/replaced,
  a badge that turned out to only exist for a younger section).
- Before claiming a badge, term, or set of sessions is "complete," check whether
  every requirement genuinely has a home somewhere in the actual files — don't
  extrapolate completeness from a summary or from memory.
- Distinguish clearly between a requirement met **as literally written**, one met
  only via a **reasonable, Scout-Association-sanctioned adaptation** ("requirements
  can be adapted to suit each young person's abilities" is real, stated Scout
  Association policy), and one that plain **cannot** be met in the context at hand
  (e.g. a cumulative multi-term total like Nights Away, or a requirement that
  mandates an external audience/event). Say which is which — don't blur them.

## Working style established for this repo

- Ask before making a structural call that has more than one reasonable
  interpretation (e.g. whether a fixed weekly slot replaces a hall meeting or sits
  alongside it) — several turns in this repo's history involved correcting a
  reasonable-but-wrong assumption made without checking first.
- Prefer auditing the actual current state of files over trusting a running mental
  model of past edits, especially after several rounds of changes.
- Small, focused git commits with a clear message per logical change; push to
  `origin/main` directly (no PR workflow in use for this repo).
