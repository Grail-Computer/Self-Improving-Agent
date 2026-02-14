# Self-Improving Agent Template

A starter template for making any project's AI coding agents compound in effectiveness over time.

## What's Inside

```
├── AGENTS.md                          # Repo memory — always-on context for agents
└── skills/
    └── self-improving-agent/
        └── SKILL.md                   # Meta-skill: how to improve AGENTS.md and create new skills
```

### [AGENTS.md](AGENTS.md)

Repository-level context that coding agents read at the start of every session. Includes:

- **Codebase Map** — so agents navigate without wandering
- **Local Norms** — build, test, style, and dependency rules
- **Guardrails** — what agents must never do
- **Patterns & Gotchas** — hard-won knowledge from past sessions
- **Self-Correction Protocol** — how this file stays alive and accurate

### [Self-Improving Agent Skill](skills/self-improving-agent/SKILL.md)

A meta-skill that teaches agents **how to improve themselves**. Covers:

- Post-task reflection (diagnose what to improve)
- Updating AGENTS.md (map, norms, guardrails, gotchas)
- Creating new skills from repeated workflows
- Scope decisions (repo-local → global → shared)
- Quality validation for improvements

## Usage

### For a New Project

1. Copy this template into your new project root.
2. Update the **Codebase Map** in `AGENTS.md` to match your project structure.
3. Replace the italicized placeholder entries with your project's actual norms.
4. Start working — the self-correction protocol will keep things current.

### Day-to-Day

- Agents read `AGENTS.md` automatically at the start of each session.
- After completing tasks, agents invoke the `self-improving-agent` skill to reflect and persist learnings.
- Over time, `AGENTS.md` accumulates the knowledge that makes each session better than the last.

### Adding New Skills

When a workflow repeats, create a new skill:

```
skills/<skill-name>/
├── SKILL.md          # The playbook
├── scripts/          # Optional helper scripts
└── examples/         # Optional reference outputs
```

See the [self-improving-agent skill](skills/self-improving-agent/SKILL.md) for the full procedure.

## The Compounding Loop

```
Work → Complete → Reflect → Record → Next task starts from a better baseline
```

Each improvement makes future improvements easier. That's how agents compound.

## Inspired By

- [Eric J. Ma — Self-Improving Coding Agents (Parts 1–3)](https://ericmjl.github.io/blog/2026/1/17/how-to-build-self-improving-coding-agents-part-1/)
- [Addy Osmani — Self-Improving Coding Agents](https://addyosmani.com/blog/self-improving-coding-agents/)
- [MaximeRobeyns — SICA Framework](https://github.com/MaximeRobeyns/self_improving_coding_agent)
- [OpenAI — Self-Evolving Agents Cookbook](https://cookbook.openai.com/examples/agent_evals_and_self_improving_loop)
