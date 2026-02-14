# AGENTS.md

> This file is the **always-on context** for any coding agent working in this repository.
> It is a living document — agents and humans should update it as the project evolves.

---

## Codebase Map

<!-- Update this section whenever the project structure changes meaningfully. -->
<!-- If you discover this map is stale, update it immediately before continuing your task. -->

```
.
├── AGENTS.md                 # This file — repo memory for agents
├── skills/                   # Reusable playbooks for agent workflows
│   └── self-improving-agent/ # Meta-skill: how to improve AGENTS.md and create new skills
│       └── SKILL.md
└── ...                       # Your project files go here
```

**Entry points:** _(Update when your project has entry points)_

- _e.g., `src/main.py`, `app/index.ts`, `cmd/server.go`_

**Configuration:** _(Update when config files exist)_

- _e.g., `pyproject.toml`, `package.json`, `.env.example`_

**Tests:** _(Update when tests are added)_

- _e.g., `tests/`, `__tests__/`, `*.test.ts`_

---

## Local Norms

<!-- These are repo-specific conventions that agents must follow. -->
<!-- Add entries here as you discover them. Keep them short and actionable. -->

### Build & Run

- _(e.g., "Use `make dev` to start the dev server")_
- _(e.g., "Use `pixi run python ...` — never bare `python`")_

### Testing

- Run all tests before marking a task as done.
- Never modify existing tests to make them pass. Fix the code instead.
- When adding a new feature, write tests that match the existing testing style in this repo.

### Code Style

- Follow the patterns already established in the codebase. When in doubt, look at adjacent files.
- _(e.g., "Use functional components, not class components")_
- _(e.g., "Prefer `pytest` fixtures over setup/teardown methods")_

### Dependencies

- Do not introduce new dependencies unless the task explicitly requires it.
- If a new dependency is needed, note it in the commit message.

### Git

- Write clear, atomic commits. One logical change per commit.
- Commit messages should describe **what** changed and **why**.

---

## Guardrails

<!-- Things the agent must NOT do. Add entries as you encounter bad agent behavior. -->

- **Never push to main directly.** Always work on a feature branch.
- **Never delete files** unless the task explicitly says to.
- **Never run destructive commands** (e.g., `rm -rf`, `DROP TABLE`) without explicit human approval.
- **Never hardcode secrets or API keys.** Use environment variables.
- **Never ignore failing tests.** If tests fail after your change, fix the code or ask for help.
- **Do not cheat by modifying tests to make them pass.**

---

## Patterns & Gotchas

<!-- Hard-won knowledge. When you discover something non-obvious, record it here. -->
<!-- Format: short statement of the gotcha, followed by what to do instead. -->

- _(e.g., "The v1/users API is deprecated — use v2/users instead.")_
- _(e.g., "When adding a new enum value, also update `constants.ts` or tests will fail.")_
- _(e.g., "The CI uses Node 20 — don't use Node 22 features.")_

---

## Skills

This repo includes reusable skills in the `skills/` directory. Skills are agent playbooks — structured instructions for repeatable workflows.

| Skill                                                        | Purpose                                                     | Trigger                                                     |
| ------------------------------------------------------------ | ----------------------------------------------------------- | ----------------------------------------------------------- |
| [self-improving-agent](skills/self-improving-agent/SKILL.md) | Improve this AGENTS.md, create new skills, encode learnings | After completing a task, or when noticing repeated friction |

### Using Skills

- Read the skill's `SKILL.md` when the trigger condition is met.
- Follow the steps exactly as written.
- If a skill's instructions are stale or wrong, update the skill.

### Creating New Skills

When a workflow repeats — especially across projects — promote it to a skill. Use the `self-improving-agent` skill for guidance on when and how.

---

## Self-Correction Protocol

> This section defines how this file stays alive and accurate.

1. **Stale map?** If you discover that the Codebase Map above doesn't match reality, **update it now** before continuing your task. Don't leave it for later.

2. **User correction?** If a human corrects your behavior (e.g., "don't use that API", "run tests this way"), add the correction to the appropriate section of this file (Local Norms, Guardrails, or Patterns & Gotchas) so future sessions inherit it.

3. **Repeated friction?** If you notice yourself doing the same multi-step workflow more than once, consider creating a new skill in `skills/`. Use the [self-improving-agent skill](skills/self-improving-agent/SKILL.md) for the procedure.

4. **Post-task reflection.** After completing a significant task, briefly review:
   - Did anything surprise you?
   - Did you take a path that could be shortcutted next time?
   - If yes, record the insight in this file or as a new skill.

---

## Template Usage

This repository is designed as a **starter template**. When integrating it into a project:

1. From the target project root, run:
   ```bash
   npx skills add "https://github.com/Grail-Computer/Self-Improving-Agent"
   ```
2. Update the **Codebase Map** to reflect your project's actual structure.
3. Update **Local Norms** with your project's build commands, test commands, and conventions.
4. Delete placeholder entries (the italicized examples) and replace with real ones.
5. Keep the **Self-Correction Protocol** and **Guardrails** — they apply universally.
6. Add project-specific skills to `skills/` as your workflows emerge.
