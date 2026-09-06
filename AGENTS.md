# AGENTS.md

Instructions for any AI agent working in this repository.

## What this repo is

A 3-year, 9-term programme plan for a UK Scout Troop (ages 10–14), converted from a
Google Doc into git specifically so it's easier to iterate on with an AI agent. The
plan is inclusive and attendance-based: Scouts earn core badge requirements during
regular weekly meetings, with optional camps/hikes/water sessions layered on top as
staged progression.

See `README.md` for the full directory layout. In short:

- `data/*.yaml` is the source of truth for the 3-year schedule and award catalogue.
- `docs/*.md` are rendered, human-readable views of that YAML.
- `year-<N>/term-<N>/` holds full session-by-session delivery plans for a term, built
  out one term at a time. **`year-1/term-1/` (World Challenge Award), `year-1/term-2/`
  (Emergency Aid Staged Activity Badge, Stage 3 — framework only so far),
  `year-1/term-3/` (Chef Activity Badge — framework only so far), `year-2/term-1/`
  (Creative Challenge Award — framework only so far), `year-2/term-2/` (Pioneer
  Activity Badge — framework only so far), `year-2/term-3/` (Global Issues Activity
  Badge — framework only so far), `year-3/term-1/` (Skills Challenge Award —
  framework only so far), `year-3/term-2/` (Scientist Activity Badge or Artist
  Activity Badge — framework only so far), and `year-3/term-3/` (Environmental
  Conservation Activity Badge — framework only so far)** are built out to date. All
  9 terms now have a theme and focus badge. Each term aims to complete exactly one
  badge in full, from a standing start, within that single term — not spread across
  multiple terms.
- Some badges are deliberately **never** a dedicated focus-badge term at all, each
  covered a different way — the group decided Outdoor Challenge Award, Adventure
  Challenge Award, Teamwork Challenge Award, Paddle Sports Staged Activity Badge
  (Stage 1), Master at Arms Activity Badge (Air Rifle / Pistol Shooting), and
  Navigator Staged Activity Badge (Stage 3/4) should be earned passively instead,
  accumulated across many terms via camps, hikes, and the standing fixed slots every
  term already has, plus a handful of standalone sessions in `filler-sessions/`.
  Expedition Challenge Award is passive too, but via the standing summer Camp and/or
  the autumn Grimsdyke Challenge Hike rather than a filler session, with each Scout
  writing their own individual report independently afterward. Team Leader Challenge
  Award and Personal Challenge Award are passive via termly leader review/discussion
  instead of a session at all. Don't propose turning any of these back into a
  dedicated term — that redesign already happened and was deliberate. All 9 real
  Challenge Awards now have a genuine home this way, with no outstanding gaps. See
  `data/awards.yaml` for how each is covered. Separately, Communicator Activity
  Badge is a complete-in-one-sitting filler (see below) rather than a guaranteed
  catalogue badge — it's opportunistic, not structurally guaranteed like the above.

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

Five fixed slots every term regardless of theme (six in Autumn terms, see Little O
below), plus the remaining weeks for term-specific badge content:

1. **Welcome Session** (`welcome-session.md`) — welcome, icebreaker, Scouts agree
   their own rules for the term, Scout-chosen games. Deliberately generic — copy it
   into a new term unchanged apart from the term name in the header. The "agree own
   rules" block also counts as one Patrol/Troop Forum occurrence towards the Teamwork
   Challenge Award (passive requirement 4), and the icebreaker should genuinely vary
   term to term so it also counts as a new team-building activity (passive
   requirement 3) — see `filler-sessions/teamwork-challenge-award.md`.
2. **End of Term Fun & Games** (`end-of-term-fun-and-games.md`) — a short badge
   presentation, then Taskmaster-style challenges. Same reuse convention as Welcome.
3. **Night Hike** (`night-hike.md`) — term-specific content, different running-order
   shape (evening/night event, not the standard 2-hour template). Should touch on the
   Countryside Code regardless of the term's own theme — this is the standing home
   for that Outdoor Challenge Award requirement (passive requirement 5); see
   `filler-sessions/outdoor-challenge-award/README.md`. It's also the standing home
   for Navigator Staged Activity Badge's real navigated routes (Stage 3's 5km route,
   Stage 4's two independent 5km compass routes) — whoever plans a Night Hike after
   the relevant `filler-sessions/navigator-stage-3.md`/`navigator-stage-4.md` session
   should make sure at least one Scout per patrol gets a genuine navigating turn.
4. **Camp** (`camp.md`) — term-specific content, multi-day running order (typically
   Friday evening–Sunday), not the standard 2-hour template. Should include a site
   walk on arrival and a leave-no-trace check before departure regardless of the
   term's own theme — the standing home for two more Outdoor Challenge Award
   requirements (passive requirements 1 and 8, Nights Away and explore/respect the
   environment).
5. **External Activity** (`external-activity.md`) — a booked, purely-for-fun outing
   (paddleboarding, a climbing wall, volleyball, etc.) **deliberately unrelated** to
   the term's theme or badge work. Treat this as a placeholder until a term's actual
   activity is booked — never fill it with theme content. Whatever gets booked counts
   towards the Adventure Challenge Award's "four different adventurous activities"
   tally (passive requirement 1) — see `filler-sessions/adventure-challenge-award.md`.
6. **Little O** (`little-o-orienteering.md`) — **Autumn terms only** (Term 1 of each
   Year). A short orienteering session in the local park, separate from the term's
   badge work. Currently a placeholder (see the file itself) — Year 1, Term 1 shipped
   before this requirement existed and doesn't have one yet; apply it starting with
   the next Autumn term built.

Night Hike, Camp, External Activity, and Little O each replace that week's normal
hall meeting rather than sitting alongside it, so the term still totals 12 weeks —
6 fixed + 6 free in Autumn terms, 5 fixed + 7 free in Spring/Summer terms.

## Filler sessions

`filler-sessions/` holds standalone sessions for when a term runs longer than its
planned content. They sit entirely outside the 9-term plan — no term theme, and
(within a badge) no dependency on any other term's sessions. Two distinct kinds live
here, and it matters which one a new file is:

**Complete-in-one-sitting badges** (`writer.md`, `entertainer.md`, `communicator-activity-badge.md`, etc.) — each
completes a full, real Scout Activity Badge in a single sitting. Before adding one:

- Check it isn't already earned elsewhere in `data/awards.yaml`.
- Verify every stated requirement can genuinely be completed in one sitting with no
  external audience, scheduled event, or take-home/multi-week component — most real
  Activity Badges are deliberately *not* single-session, so this rules out more
  candidates than it allows. Record which of "no adaptation," "no adaptation but
  needs specific access" (e.g. green space), or "light adaptation" applies, and say
  exactly what the adaptation is if there is one.
- Header uses **Badge:**, **Why it's a good filler:**, and **Adaptation needed:**
  instead of the term-specific `Term:`/`Fits the term because:` fields.

**Passive-progress badges** (`filler-sessions/outdoor-challenge-award/`,
`adventure-challenge-award.md`, `teamwork-challenge-award.md`,
`paddle-sports-staged-activity-badge.md`, `master-at-arms-activity-badge.md`,
`navigator-stage-3.md`, `navigator-stage-4.md`) — for
badges the group has decided are earned passively across many terms rather than in
one sitting or one term (currently Outdoor, Adventure, and Teamwork Challenge
Awards, Paddle Sports Staged Activity Badge Stage 1, Master at Arms Activity
Badge, and Navigator Staged Activity Badge Stage 3/4). Not every passive badge gets
a file here, though — Team Leader Challenge Award and Personal Challenge Award are
passive via termly leader review instead, and Expedition Challenge Award via the
standing summer Camp/Grimsdyke Challenge Hike plus an independently-written report;
none of the three need a dedicated session. Each file that does exist here covers one
or a few requirements, not the whole badge, and is explicit about which
requirements accumulate elsewhere (standing fixed slots, other terms) with no
dedicated session at all. Multi-file badges (like Outdoor and Navigator) either get
their own subdirectory with a `README.md` mapping every requirement to a session or
a standing slot (Outdoor), or — when the split is simple enough to be obvious from
filenames alone, like Navigator's two stages — just multiple flat files with no
index needed. Header uses **Badge:**, **Why this works as a filler:**, and
**Requirement(s) this session covers:** — and should name which requirements are
covered passively elsewhere, not just which this file covers.

## Passive badge completion

Every term's regular content (games, camps, hikes, teamwork/leadership activities)
sometimes advances real requirements of *other* Scouts-section badges as a side
effect, without any dedicated session time for them. This is worth surfacing but
easy to overclaim, so when a term is built (or revisited):

- Prioritise checking badges with an obvious thematic overlap with what the term
  already does (e.g. a term with an environmental placement is worth checking against
  Environmental Conservation; a term with international contact is worth checking
  against the International Activity Badge). Don't attempt an exhaustive sweep of
  every Scouts-section badge — that's explicitly out of scope per the group's own
  guidance, not an oversight.
- Fetch the real requirement wording for each candidate badge before claiming
  anything, same as for the term's focus badge.
- Be explicit about **full vs. partial** overlap. A badge should only be described as
  passively "earned" if every one of its requirements is genuinely met; if only some
  requirements line up (the far more common case), say so plainly and don't record it
  as earned in `data/awards.yaml` — partial progress lives in the term's own
  `overview.md` under a **Passive completion** heading, not the data files.
- This is in addition to, not instead of, each term's single focus badge — the goal
  is still one badge started and finished within a single term, with anything else
  picked up passively treated as a bonus, never a substitute.

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
- **Every term's `overview.md` ends with a material inventory.** Pull every
  `**Materials:**` line from that term's session files, consolidate, and quantify for
  the group's stated maximum of 6 patrols (e.g. "6 patrol tents", not "1 tent per
  patrol"), grouped into sensible categories with a link back to which session(s) use
  each item. Regenerate this whenever a session's materials change — don't let it
  drift from what the session files actually say.

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
