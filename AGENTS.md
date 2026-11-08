# Instructions for AI agents working in this repository

This is the shared, harness-neutral brief for every agent that works here (Claude Code, Copilot, Codex, Hermes and others). Harness-specific files such as `CLAUDE.md` and `.github/copilot-instructions.md` only point here.

## Ground rules

- **Never commit secrets.** No API keys, tokens, passwords, private keys or `.env` files. Use `.env` (gitignored) and keep `.env.example` current. If you find a secret in the repository, stop and report it; do not try to rewrite history yourself.
- **Never push to `main`.** Work on a branch named `agent/<identity>/<short-task>` (for example `agent/drishdigreen/fix-retry-loop`) and open a pull request.
- **One task per pull request.** Keep changes small enough for a human to review in a few minutes.
- **Docs are the source of truth.** When you change behaviour, update the matching doc. Significant or hard-to-reverse decisions get an ADR in `docs/decisions/` (copy `0000-template.md`).
- **State what you did not verify.** If tests were not run or a claim was not checked, say so in the pull request. Do not overstate results.

## Identity and attribution

Every commit made by an agent ends with trailers that say who did the work:

```
Agent: <identity, e.g. drishdigreen>
Agent-Model: <model and version>
Agent-Harness: <e.g. Claude Code, Copilot, Codex, Hermes>
```

Pull requests use the same identity in the title prefix, for example `[drishdigreen] Fix retry loop in fetcher`.

## Review and critique

The work is only accepted when a different agent, or a human, has reviewed it.

- **Reviewers must differ from authors.** An agent never approves its own work. Where possible the reviewer uses a different model family or harness from the author.
- **Critique, do not rubber-stamp.** A review states what is wrong or risky, offers at least one alternative approach where one exists, and says what would change the reviewer's mind.
- **Check the evidence.** Run the tests or the reproduction steps. A review that only reads the diff must say so.
- **Disagreement is recorded, not hidden.** If author and reviewer disagree, leave both positions in the pull request for the human to decide.

## Issues

- Open an issue for any problem you find that is outside your task, rather than fixing it silently.
- Label issues `agent-task` when they are suitable for an agent to pick up, and say which skills or context they need.

## Before opening a pull request

- [ ] Tests and linters pass locally, or the pull request says why not
- [ ] No secrets, credentials or personal data in the diff
- [ ] Docs and ADRs updated if behaviour changed
- [ ] Commit trailers present
