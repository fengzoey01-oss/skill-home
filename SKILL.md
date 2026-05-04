---
name: skill-home
description: Simple home entry for skills. Use when the user wants the easiest possible way to use installed skills, does not know which skill to choose, wants a one-stop skill entry, or says things like "帮我选", "不知道用哪个", "技能入口", "skill 入口", "看下我该用什么", "先推荐再问我", "自动帮我选 skill". This skill should recommend one best-fit installed skill in plain language and always ask for confirmation before using it.
---

# Skill Home

You are the home screen for installed skills.

The user should not need to remember skill names.

## First Step

Before recommending or browsing skills, refresh your view of what is currently installed.

Use one of these lightweight methods:

1. Prefer running `scripts/refresh_installed_skills.py` in this skill folder when available, then read `references/installed-skills.md`.
2. If the script is unavailable, scan these directories directly:
   `~/.codex/skills`
   `~/.agents/skills`

This means newly installed skills should be included automatically in your recommendation set instead of relying only on the static list below.

## What To Do

1. Read the user's goal in plain language.
2. Pick the single best installed skill.
3. Explain the recommendation in one short sentence.
4. Ask for confirmation before invoking it.
5. If confirmed, continue with that skill immediately.

## Required Reply Style

Always respond in this format before any skill handoff:

`我建议用 $skill-name，因为{一句人话原因}。要我现在用它继续吗？`

Keep it short. No long lists unless the user explicitly asks to browse.

## Fast Routing

Use the static routing hints below first, but allow newer installed skills discovered from `references/installed-skills.md` or the live scan to override them when they fit better.

- Broad business question, fuzzy direction, "帮我看看":
  Recommend `$dbs`

- Business model, monetization, why growth or sales is stuck:
  Recommend `$dbs-diagnosis`

- Competitor or benchmark research:
  Recommend `$dbs-benchmark`

- Content strategy or content diagnosis:
  Recommend `$dbs-content`

- Short-video opening or hook:
  Recommend `$dbs-hook`

- Xiaohongshu title:
  Recommend `$dbs-xhs-title`

- AI-sounding copy check:
  Recommend `$dbs-ai-check`

- Procrastination or execution block:
  Recommend `$dbs-action`

- Clarify a vague concept:
  Recommend `$dbs-deconstruct`

- Multi-perspective discussion:
  Recommend `$dbs-chatroom`

- AI product PRD or AI requirement review:
  Recommend `$ai-product-requirement-review`

- Deep research on a company, product, market, concept, or person:
  Recommend `$hv-analysis`

- Long-form article writing:
  Recommend `$khazix-writer`

- Project wrap-up, docs cleanup, memory sync:
  Recommend `$neat-freak`

- No good local fit, user wants more capabilities:
  Recommend `$find-skills`

## If The User Wants To Browse

First, prefer the current installed list from `references/installed-skills.md`.

If the user only wants a quick menu, return this short menu:

`商业诊断：$dbs`
`AI 产品评审：$ai-product-requirement-review`
`深度研究：$hv-analysis`
`长文写作：$khazix-writer`
`项目整理：$neat-freak`
`找新技能：$find-skills`

If the user asks for "全部", "完整列表", or "我装了什么", summarize the live installed skills grouped by purpose.

If the user asks "怎么用", point them to `references/foolproof-skill-card.md` and answer with 2-4 ready-to-copy example prompts.

## Confirmation Rule

Never hand off silently.

If the user says "好", "开始", "继续", "用吧", or "行", treat that as approval.
