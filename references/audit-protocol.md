# Audit protocol

## Cache

The source manuscript is authoritative. A cached audit is clean only when the
source has not changed since the cache was generated. `audit /refresh` is the
explicit recomputation command. A normal `audit` reads the cache and must not
silently recompute it.

The copyedit cache follows the same rule. `audit copyedit` reports its status;
`audit copyedit fix` changes the source and therefore invalidates the cache until
the audit is refreshed.

## Flags and ratings

- `[X]`: complete, satisfactory, or independently accepted as adequate.
- `[ ]`: an actionable unresolved issue remains.
- `[N/A]`: the author consciously chooses not to change it; do not keep treating
  it as unfinished work.

Ratings describe current manuscript quality, not the number of unchecked boxes.
When every subitem has been resolved, raise the parent rating substantially. If
it is still below 10, identify a new actionable higher-value issue rather than
leaving the score low without an explanation.

## Output

Use exactly this compact shape:

```text
Tier 1

 1. [X] (8/10) Title - short description
...
10. [ ] (7/10) Title - short description

Tier 2

11. [X] (8/10) Title - short description
...
20. [ ] (7/10) Title - short description
```

Pad item numbers 1–9 with one extra space after the period so the opening flag
aligns with item 10. Keep each complete line no longer than 110 characters.

## Copyediting categories

- Zero guidance: safe mechanical correction with no meaningful authorial choice.
- Guidance required: plausible improvement whose wording, tone, or intent needs
  author confirmation.
- Human only: requires factual, legal, continuity, taste, or authorial judgment.

Do not confuse copyediting counts with the overall prose score. Eliminating all
mechanical errors can improve item 20 but does not automatically make broader
line editing, voice, rhythm, or style a 10/10.
