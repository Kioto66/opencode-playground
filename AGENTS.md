# AGENTS.md

## What this repo is

A throwaway practice sandbox for learning Git and AI agents (see `README.md`). It is
intentionally empty of tooling.

## No toolchain — this is the main thing to know

There is no build, test, lint, typecheck, or codegen step. No `package.json`,
`pyproject.toml`, `Makefile`, CI workflow, or pre-commit config exists, and none is
expected.

- Do not invent a toolchain or scaffold one "to be helpful."
- Do not guess or run verification commands (`npm test`, `pytest`, `make`, `tsc`) —
  they will fail, and a failing command you added yourself is noise, not a finding.
- Do not add a `lint -> typecheck -> test` habit here. There is nothing to check.
- Verification for a change in this repo is `git status` / `git diff` review only.

## Verify before asserting

With no tests to lean on, confirm claims by reading the actual files and
`git log`/`git status`. State what you checked rather than assuming repo state.

## Adding files

`.gitignore` already pre-covers Python, Node, build output, logs, editor dirs, and
secret file types (`.env`, `*.pem`, `*.key`, `*.pfx`). Don't extend it for a stack
you're adding — it is handled. Never commit anything matching those secret patterns.

`README.md` is written in Russian. Match that language if you extend the docs.

## Git

Default flow, no project conventions: commit directly to `main` with plain commit
messages. Only commit when explicitly asked.


## Agent safety rules

- Start every non-trivial task by proposing a short plan. Do not edit files until the user approves the plan or explicitly asks to implement it.
- Before applying edits, state which files will be changed and why.
- Do not run destructive or environment-changing commands without explicit approval. This includes deleting files, changing Git history, installing packages, changing system settings, or starting network services.
- Do not read, display, copy, upload, or request secrets: passwords, API keys, browser profiles, authentication files, tokens, `.env` files, private keys, certificates, or production configuration.
- Do not send project files, logs, databases, exports, or documents to external services unless the user explicitly approves it.
- Prefer small, isolated changes. Do not refactor unrelated code.
- After an edit, show a concise summary and ask the user to review `git diff`.