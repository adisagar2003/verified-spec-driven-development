# Verified Spec-Driven Development (VSDD)

<img width="1400" height="1400" alt="image" src="https://github.com/user-attachments/assets/290de7e7-7da7-4d07-9198-fba7a4defe33" />

An [Agent Skill](https://agentskills.io) for AI-assisted engineering — a structured workflow that helps engineers build software with AI without outsourcing their thinking.

Combines spec-driven development, test-driven development, and adversarial review into a practical step-by-step process.

## Install

### Claude Code (personal — available in all projects)

```bash
mkdir -p ~/.claude/skills/verified-spec-driven-development
curl -o ~/.claude/skills/verified-spec-driven-development/SKILL.md \
  https://raw.githubusercontent.com/adisagar2003/verified-spec-driven-development/main/verified-spec-driven-development/SKILL.md
```

### Claude Code (project — shared with your team)

```bash
mkdir -p .claude/skills/verified-spec-driven-development
curl -o .claude/skills/verified-spec-driven-development/SKILL.md \
  https://raw.githubusercontent.com/adisagar2003/verified-spec-driven-development/main/verified-spec-driven-development/SKILL.md
```

### VS Code / GitHub Copilot (Agent mode)

```bash
mkdir -p .agents/skills/verified-spec-driven-development
curl -o .agents/skills/verified-spec-driven-development/SKILL.md \
  https://raw.githubusercontent.com/adisagar2003/verified-spec-driven-development/main/verified-spec-driven-development/SKILL.md
```

### Any other agent

Copy `verified-spec-driven-development/SKILL.md` into your agent's skill directory.

## Usage

Once installed, the skill activates automatically when you start a new feature or project. Or invoke it directly:

```
/verified-spec-driven-development
```

## What It Does

Guides you through six steps for any new feature or project:

1. **Understand** — Use AI to explore the codebase (diagrams, architecture overviews)
2. **Spec** — You write the spec, AI stress-tests it for gaps
3. **Layer** — Break work into buildable layers (types -> logic -> API -> UI)
4. **Build** — Test-first for each layer (Red -> Green -> Refactor)
5. **Review** — Fresh AI context reviews for blind spots
6. **Ship** — Harden and deliver

## Based On

- [VSDD Methodology](https://gist.github.com/dollspace-gay/d8d3bc3ecf4188df049d7a4726bb2a00) — The six-phase spec-first, test-first, adversarially-refined pipeline
- ["Vibe Coding Does NOT Equal AI-Assisted"](https://www.linkedin.com/pulse/vibe-coding-does-equal-ai-assisted-samuel-gregory-ec9wf/) by Samuel Gregory — The distinction between prompting and engineering

## Compatibility

Works with any AI coding assistant that supports the [Agent Skills](https://agentskills.io/specification) format:
- [Claude Code](https://code.claude.com/docs/en/skills)
- VS Code (GitHub Copilot Agent mode)
- Cursor / Windsurf
- OpenAI Codex

## License

MIT
