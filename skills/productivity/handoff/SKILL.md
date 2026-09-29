---
name: handoff
description: Compact the current conversation into a handoff document for another agent to pick up.
argument-hint: "[focus of the next session]"
disable-model-invocation: true
---

Write a handoff document so a fresh agent with none of this conversation's context can continue the work.

Next session's focus (may be empty): $ARGUMENTS
If given, tailor the document to it and leave out anything irrelevant to it.

## Where
Save to `~/.claude/handoffs/<YYYY-MM-DD>-<repo-or-topic>-<short-slug>.md` (create the directory if needed).
Never save inside the current workspace. Never overwrite an existing handoff.

## Contents
Use these sections; omit any that would be empty:
- **Goal**: what we are trying to achieve and why.
- **Context**: absolute repo path(s), branch, HEAD SHA, summary of uncommitted changes (`git status`).
- **Current state**: what is done, what is in progress.
- **Decisions**: choices made and the reason for each, including options rejected.
- **Dead ends**: approaches tried that failed, and why, so they aren't retried.
- **Next steps**: ordered, concrete, each one actionable.
- **Open questions**: things only the user can decide.
- **References**: PRDs, plans, ADRs, issues, PRs, commits: link by path or URL; do not restate their content.
- **Suggested skills**: only skills from your available-skills list, each with when to use it.

Mark any claim you did not verify against a file or command output as *(unverified)*.

## Rules
- Redact secrets, credentials, tokens, personal data, and customer data.
- Be concise: the next agent can read files; give it pointers, not copies.

## When done
Print the absolute path and a one-line prompt the user can paste into a new session, e.g.
`Read <path> and continue from "Next steps".` Then stop; do not start the next steps yourself.
