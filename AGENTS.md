# AGENTS.md — instructions for cloud coding agents (Cursor / Grok Bot)

This repo is an AI game studio template originally built for Claude Code. Here,
work is coordinated by Grok Bot (producer) and code is written by cloud coding agents.
Slash commands (`/dev-story` etc.) and `.claude/hooks` do NOT run automatically —
follow the equivalent files by hand.

## Before any task
1. Read `CLAUDE.md` (studio overview, tech stack, collaboration protocol) and the docs it references.
2. Read every relevant file in `.claude/rules/` (e.g. `gameplay-code.md`, `engine-code.md`,
   `ui-code.md`, `ai-code.md`, `test-standards.md`, `data-files.md`, `design-docs.md`).
3. Act as the role named in the task: read `.claude/agents/<role>.md` and follow its
   responsibilities, boundaries and escalation rules. If no role is named, pick the closest
   specialist (e.g. gameplay-programmer, ui-programmer, qa-tester) and say which one you used.
4. If the task names a workflow (e.g. "dev-story", "story-done", "code-review"), read
   `.claude/skills/<workflow>/SKILL.md` and execute its steps manually.

## Working rules
- Work on a feature branch and open a pull request; never push to `main`.
- Implement against the story's acceptance criteria and relevant GDD/ADR in `design/` and `docs/`.
- Add or update tests per `.claude/rules/test-standards.md`.
- Manually apply what the hooks would check (see `.claude/hooks/validate-commit.sh`,
  `validate-push.sh`, `validate-assets.sh`): commit message format, no secrets, asset naming.
- Update story status / production docs in `production/` when a story is completed.
- You cannot run the game engine with a GPU; note in the PR what needs playtesting on the
  studio head's PC (Unity CLI builds run there).
