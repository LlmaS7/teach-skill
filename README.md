# Personalized `teach` skill

A modified, single-skill version of Matt Pocock's `teach` skill for guided, multi-session learning in a stateful workspace.

## What this version adds

- Before the first lesson, it gives a concise learning roadmap once the learner's mission is clear. The roadmap is provisional and can change as the learner progresses.
- Markdown is the default lesson format; HTML is used only when explicitly requested.

## Files

- `SKILL.md` — the skill instructions.
- `agents/openai.yaml` — display metadata and invocation policy.
- `GLOSSARY-FORMAT.md`, `LEARNING-RECORD-FORMAT.md`, `MISSION-FORMAT.md`, and `RESOURCES-FORMAT.md` — formats for the teaching workspace files.
- `LICENSE` — the upstream MIT license notice.

## Upstream and license

This repository is an independent adaptation of the [`teach` skill](https://github.com/mattpocock/skills/tree/main/skills/productivity/teach) from [mattpocock/skills](https://github.com/mattpocock/skills). The upstream project is distributed under the MIT License; its copyright and license notice are retained in `LICENSE`.

This repository is not affiliated with or endorsed by Matt Pocock.
