# Personalized `teach` skill | 个性化 `teach` 技能

## English

### Overview

An independent adaptation of Matt Pocock's `teach` skill for guided, multi-session learning in a stateful workspace.

### What this version adds

- Before the first lesson, it provides a concise learning roadmap once the learner's mission is clear. The roadmap is provisional and can change as the learner progresses.
- Markdown is the default lesson format; HTML is used only when explicitly requested.

### Files

- `SKILL.md` - skill instructions.
- `agents/openai.yaml` - display metadata and invocation policy.
- `GLOSSARY-FORMAT.md`, `LEARNING-RECORD-FORMAT.md`, `MISSION-FORMAT.md`, and `RESOURCES-FORMAT.md` - formats for the teaching workspace files.
- `LICENSE` - the upstream MIT license notice.

### Attribution and license

This repository adapts the [`teach` skill](https://github.com/mattpocock/skills/tree/main/skills/productivity/teach) from [mattpocock/skills](https://github.com/mattpocock/skills). The upstream project is distributed under the MIT License. Its copyright and license notice are retained in `LICENSE`.

This repository is not affiliated with or endorsed by Matt Pocock.

### Install in Codex

Place this skill directory in your Codex skills folder as `teach` (for example, `~/.codex/skills/teach`).

## 中文

### 简介

这是基于 Matt Pocock 的 `teach` skill 改写的独立版本，用于在持续保存学习进度的工作区中开展多轮教学。

### 本版本的调整

- 在学习目标明确后、第一课开始前，先给出简短的参考学习路线图；后续可根据学习进度调整。
- 默认使用 Markdown 编写课程内容；只有用户明确要求时才使用 HTML。

### 文件说明

- `SKILL.md` - skill 的教学规则。
- `agents/openai.yaml` - 显示信息与调用策略。
- `GLOSSARY-FORMAT.md`、`LEARNING-RECORD-FORMAT.md`、`MISSION-FORMAT.md`、`RESOURCES-FORMAT.md` - 教学工作区各类文件的格式说明。
- `LICENSE` - 上游 MIT 许可证及版权声明。

### 来源与许可

本仓库改编自 [Matt Pocock 的 `teach` skill](https://github.com/mattpocock/skills/tree/main/skills/productivity/teach)，来源仓库为 [mattpocock/skills](https://github.com/mattpocock/skills)。上游项目采用 MIT 许可证，相关版权与许可声明保留在 `LICENSE` 中。

本仓库为独立改版，与 Matt Pocock 无隶属或背书关系。

### 在 Codex 中安装

将本 skill 目录放入 Codex 的 skills 目录，并命名为 `teach`，例如 `~/.codex/skills/teach`。