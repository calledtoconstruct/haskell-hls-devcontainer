# Guiding principles: calledtoconstruct/haskell-hls-devcontainer

## Purpose and scope
A VS Code dev container for Haskell with Haskell Language Server, ported from haskell-hie-devcontainer.

## Stack and layout
`.devcontainer/devcontainer.json` (GHC 8.6.5 with HLS and ghcide, user `vscode`, Haskell extension) and the Dockerfile it references.

## Commands
| Check | Command | Evidence |
|---|---|---|
| Build | Reopen in Container in VS Code (the README's method); there is no scripted build | README.md |
| Lint | None | - |
| Tests | None | repository tree |
| CI | None | repository tree |

Commands marked as not written down come from the build files, not from project docs; confirm them before relying on them.

## Before every push
Before every push: run the build and type-check/lint that exist here, plus only the tests for the files or feature you changed (team rule, ideas #14 note 6797). Do not run the full suite locally as a routine gate; this repository has no CI that runs the full suite, so run the full suite only when the change is broad, and say in the PR that CI coverage is missing. Merge needs a positive review. Explain any new failure your change caused. Never weaken a valid test to make it pass, and never invent a command this file does not list.

## Project rules
- Users copy `.devcontainer/` into their own projects; keep it self-contained and keep paths relative.
- Keep the README's 'What's in the box' list in step with the Dockerfile.

## What to avoid
- Committing to the default branch; work on a branch and open a pull request.
- Deleting files, branches or history, or changing repository settings.
- Adding tooling, CI or dependencies that the change does not need.
- Rules copied from other projects (file-size limits, clocks, quotas) that this repository never adopted.

## Delivery and safety
- Nothing is published.

## Open questions
- Whether the pinned GHC/HLS versions still build was not checked.

## Sources
Read from the `main` branch on 2026-11-08 ET: `README.md`, `.devcontainer/devcontainer.json`.

## Instruction updates
Check `guiding-principles.version` at the start of each turn and when you enter this project; reload this file when the version changes. Change this file, its version and date, and `PRINCIPLES_HISTORY.md` in the same commit. Team-wide role instructions are versioned separately in the team-process repository.
