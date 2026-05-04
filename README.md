# skill-home

A simple home entry for Codex skills.

`skill-home` is designed for one very practical problem: once you install more and more skills, it becomes hard to remember which one to use for a given task.

Instead of forcing the user to memorize skill names, `skill-home` lets the user speak naturally, recommends the best-fit installed skill, and asks for confirmation before using it.

## What it does

- Recommends the best installed skill for the user's goal
- Explains the recommendation in plain language
- Always asks before invoking another skill
- Scans installed skills dynamically from local skill directories
- Includes a foolproof prompt card for copy-paste usage

## Best for

- Users who do not know which skill to use
- Users who want one entry point instead of memorizing many skill names
- Teams sharing a growing local skill collection
- Codex setups where new skills are added over time

## Example prompts

```text
用 $skill-home 帮我选
用 $skill-home 看看这件事该用哪个 skill
用 $skill-home 我不知道该用什么
用 $skill-home 先推荐，再问我确认
用 $skill-home 看看我现在装了哪些 skill
```

## Structure

```text
.
├── SKILL.md
├── README.md
├── agents/
│   └── openai.yaml
├── references/
│   └── foolproof-skill-card.md
└── scripts/
    └── refresh_installed_skills.py
```

## Notes

- `installed-skills.md` is intentionally not committed because it is generated locally and may contain machine-specific paths.
- The skill is designed to scan `~/.codex/skills` and `~/.agents/skills`, or generate a current index by running `scripts/refresh_installed_skills.py`.

## Install manually

Copy this folder into your Codex skills directory:

```text
~/.codex/skills/skill-home
```

Then restart Codex.

## Core idea

This is not a "more powerful skill".

It is a cleaner entry point for an already powerful skill system.

The goal is simple:

- You do not need to memorize skill names
- You do not need to understand the internal routing
- You can just describe your goal, get a recommendation, and confirm
