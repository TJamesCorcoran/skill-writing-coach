# Writing Coach skill

Writing Coach is a reusable agent skill for reviewing and improving manuscripts.
It provides a structured 20-point writing audit, cached audit commands, detailed
subitem investigation, copyediting triage, and practical revision guidance.

## Features

- Tiered 20-point manuscript review covering characterization, structure, pacing,
  causality, stakes, voice, dialogue, continuity, and line-level prose.
- Cached audits that distinguish ordinary review from an explicit refresh.
- Detailed findings with `x.y` item/subitem addressing.
- Deep investigation with `audit details x.y expand`.
- Copyediting categories for zero-guidance, guidance-required, and human-only work.
- POV-switch evaluation using core and optional reader-orientation anchors.
- Consistent `[X]`, `[ ]`, and `[N/A]` review statuses.
- Actionable revision locations using chapter names and searchable text strings.

## Installation

Install the skill by cloning its repository into the agent's personal skills
directory:

```bash
cd ~/.codex/skills ; git clone https://github.com/TJamesCorcoran/skill-writing-coach.git
```

For a Codex installation with `CODEX_HOME` set, use:

```bash
cd "$CODEX_HOME/skills" ; git clone https://github.com/TJamesCorcoran/skill-writing-coach.git
```

After installation, point the skill at the manuscript:

```text
audit init /path/to/story.txt
```

This verifies the file and binds the active manuscript, cache, and `audit.txt`
locations. It also loads adjacent project memory when available.

The package must contain `SKILL.md` at its top level. The `agents/openai.yaml`
file provides optional display metadata; the files under `references/` contain
the detailed audit and POV guidance.

## Use

Invoke it explicitly with `$writing-coach`, or let the agent select it for a
manuscript-review request when implicit skill invocation is enabled.

The command protocol is:

```text
help
audit
audit init <filepath>
audit /refresh
audit /write
audit cache status
audit copyedit
audit copyedit fix
audit details x.y
audit details x.y --all
audit details x.y expand
```

The skill contains reusable review behavior only. Keep the manuscript, project
memory, current ratings, and audit cache in the relevant writing project rather
than embedding them in this package.
