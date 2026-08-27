---
name: writing-coach
description: Review and improve manuscripts using the user's 20-point audit, cached audit commands, POV-anchor rules, and actionable chapter/search-location guidance.
---

# Writing Coach

Use this skill for manuscript review, revision advice, character work, structure,
POV, pacing, prose, copyediting, or the `audit` command family.

## Operating rules

1. Identify the active writing project and its canonical memory file before making
   project-specific claims. Read the relevant memory and the current manuscript
   when a fresh reading is requested.
2. Keep manuscript facts, current ratings, resolved subitems, and audit cache in
   the project directory—not in this reusable skill.
3. `audit` uses the cached audit unless the user explicitly requests a refresh.
   Say whether the cache is clean or dirty as the first line of `audit` output.
4. Do not mechanically clear findings because the author disputes them. For
   `expand`, investigate independently and retain a finding when it remains
   actionable.
5. When proposing a book change, provide its chapter and an exact searchable
   text string. If the user asks only for general advice, this location rule is
   unnecessary.
6. Use `[X]` for complete or satisfactory, `[ ]` for unresolved, and `[N/A]`
   for a consciously accepted non-change. A resolved subitem must improve its
   parent rating or produce a new, concrete higher-value action.
7. Format audit items as `n. [flag] (score/10) TITLE - description`, with
   whitespace after the ordinal so every flag starts in the same column. Put a
   visible break between Tier 1 items 1–10 and Tier 2 items 11–20. Keep audit
   lines to at most 110 characters, including fields and whitespace.
8. Preserve intentional omniscient passages and other declared authorial style
   choices. Evaluate transitions and execution rather than repeatedly proposing
   removal of an accepted style choice.

## Commands

- `help`: list every command below, including copyedit subcommands.
- `audit`: display the cached 20-point audit, beginning with `cache clean` or
  `cache dirty`.
- `audit /refresh`: reread the manuscript, recompute the audit, refresh the
  cache, and display the newly cached audit.
- `audit /write`: write the current audit to `audit.txt` beside `story.txt`.
- `audit cache status`: report source/cache timestamps and cache validity.
- `audit copyedit`: display cached copyedit counts. Begin with cache status, then
  exactly three bullets: zero-guidance errors, guidance-required errors, and
  human-only errors.
- `audit copyedit fix`: fix all zero-guidance copyediting errors, then report
  what changed and whether the copyedit cache is dirty.
- `audit details x.y`: list findings or suggestions for item `x`, subitem `y`,
  clipped to the top ten by default.
- `audit details x.y --all`: list every finding for that subitem.
- `audit details x.y expand`: investigate deeply; state clearly if the concern
  is not real, otherwise explain the precise problem and fix.

`x.y` is always shorthand for “item x, subitem y.” For example, `18.5` means
continuity item 18, subitem 5.

## POV switches

Use the complete anchor set in `references/pov-switches.md`. The three core
anchors are character name, physical location, and sensory input filtered through
that character. A clear 3/3 transition merits at least 7/10, normally 8/10 or
higher. Other anchors are useful but optional and may add fractional credit.

## Audit framework

Use `references/review-criteria.md` for the 20 categories and
`references/audit-protocol.md` for scoring, flags, cache behavior, and output.
