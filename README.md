# DevOps Skills

A pruned, DevOps-focused fork of [Matt Pocock's agent skills](https://github.com/mattpocock/skills) for Claude Code.

The original repo is aimed at application development (TDD, PRD → issues → implement, domain modeling). This fork keeps only the skills useful for infrastructure/ops work — Terraform, Kubernetes, CI/CD pipelines — and drops everything tied to a specific issue-tracker workflow or app-dev practice this team doesn't use.

## Install

Symlink every skill into your local Claude Code / Agent-Skills harness:

```bash
scripts/link-skills.sh
```

Or install selectively via [skills.sh](https://skills.sh):

```bash
npx skills@latest add kave-h/skills
```

## Skills

### Engineering

Skills for day-to-day infra/ops work — see [skills/engineering/README.md](./skills/engineering/README.md) for details.

- **[diagnosing-bugs](./skills/engineering/diagnosing-bugs/SKILL.md)** — Disciplined diagnosis loop for hard bugs and regressions.
- **[research](./skills/engineering/research/SKILL.md)** — Investigate a question against primary sources, run as a background agent.
- **[resolving-merge-conflicts](./skills/engineering/resolving-merge-conflicts/SKILL.md)** — Resolve an in-progress git merge/rebase conflict.
- **[code-review](./skills/engineering/code-review/SKILL.md)** — Two-axis review (Standards + Spec) of a diff.
- **[git-guardrails-claude-code](./skills/engineering/git-guardrails-claude-code/SKILL.md)** — Hooks that block dangerous git commands before they execute.

### Productivity

General workflow tools — see [skills/productivity/README.md](./skills/productivity/README.md) for details.

- **[grill-me](./skills/productivity/grill-me/SKILL.md)** — Get relentlessly interviewed about a plan or design until every branch is resolved.
- **[grilling](./skills/productivity/grilling/SKILL.md)** — The reusable interview loop behind `grill-me`.
- **[handoff](./skills/productivity/handoff/SKILL.md)** — Compact the current conversation into a handoff document for another agent/session.
- **[writing-great-skills](./skills/productivity/writing-great-skills/SKILL.md)** — Reference for writing and editing skills well.

## Why fork instead of using upstream directly

- Upstream's issue-tracker skills (`to-issues`, `to-prd`, `triage`) only support GitHub, GitLab, and Backlog.md — not Azure DevOps, which this team uses.
- Most of upstream's flow (`tdd`, `domain-modeling`, `codebase-design`, `improve-codebase-architecture`, `implement`) is built around application feature work, not infrastructure change.
- Fewer skills means less to hold in your head before reaching for one — the whole point of forking was simplicity.

`upstream` remote still points at `mattpocock/skills` if you want to pull in a fix or a new skill worth adapting.

## License

MIT, inherited from the upstream project.
