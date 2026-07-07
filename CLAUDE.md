This is a pruned fork of [mattpocock/skills](https://github.com/mattpocock/skills), kept deliberately small — DevOps/IaC skills only, no app-dev workflow, no issue-tracker-specific automation. Bias toward keeping it small: don't re-add a skill (or upstream's bucket/docs-page/router scaffolding) unless it earns its keep.

Skills live in two bucket folders under `skills/`:

- `engineering/` — day-to-day infra/ops work (diagnosing issues, reviewing diffs, git safety)
- `productivity/` — general workflow tools, not code-specific

Every skill must have a reference in the top-level `README.md` and an entry in `.claude-plugin/plugin.json`. Each bucket folder has a `README.md` that lists every skill in that bucket with a one-line description, linking the skill name to its `SKILL.md`.

Every `SKILL.md` is either user-invoked (`disable-model-invocation: true`, reachable only by typing it) or model-invoked (reachable by the model or the user). See [.agents/invocation.md](./.agents/invocation.md).

To (re)link every skill into the local harness skill directories (`~/.claude/skills`, `~/.agents/skills`), run `scripts/link-skills.sh`. Each entry is a symlink into this repo, so a `git pull` keeps installed skills current; re-run the script after adding, removing, or renaming a skill.

`upstream` remote points at `mattpocock/skills` — pull from it deliberately when a specific fix or skill upstream is worth adapting, don't merge wholesale.
