# Engineering

Skills for day-to-day infra/ops work: diagnosing problems, reviewing changes, researching before acting, and staying safe in git.

All of these are model-invoked — reachable by name or by the agent reaching for them automatically when the task fits.

- **[diagnosing-bugs](./diagnosing-bugs/SKILL.md)** — Disciplined diagnosis loop for hard bugs and regressions: reproduce → minimise → hypothesise → instrument → fix → regression-test.
- **[research](./research/SKILL.md)** — Investigate a question against high-trust primary sources and capture the findings as a cited Markdown file in the repo, run as a background agent.
- **[resolving-merge-conflicts](./resolving-merge-conflicts/SKILL.md)** — Resolve an in-progress git merge/rebase conflict.
- **[code-review](./code-review/SKILL.md)** — Two-axis review of the diff since a fixed point: **Standards** (does it follow the repo's documented coding standards?) and **Spec** (does it match what was asked for?), run as parallel sub-agents.
- **[git-guardrails-claude-code](./git-guardrails-claude-code/SKILL.md)** — Set up Claude Code hooks that block dangerous git commands (push, reset --hard, clean, branch -D) before they execute.
