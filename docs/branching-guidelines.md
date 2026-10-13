# Branching Guidelines

These conventions keep team changes isolated, reviewable, and traceable to Jira tasks.

## 1. Main branch

- `main` is the shared stable branch.
- Do not commit task work directly to `main`.
- Changes should reach `main` through a pull request after review and any required checks pass.

## 2. Branch naming

Create a short-lived branch from the latest `main` for each task. Use a lowercase type and a short, hyphen-separated description:

| Work type | Naming pattern | Example |
| --- | --- | --- |
| New feature | `feat/<short-description>` | `feat/booking-search` |
| Bug fix | `fix/<short-description>` | `fix/date-validation` |
| Documentation | `docs/<short-description>` | `docs/branching-guidelines` |
| Maintenance / setup | `chore/<short-description>` | `chore/base-folder-structure` |
| Tests | `test/<short-description>` | `test/booking-api` |

If practical, include the Jira key in the branch name, for example `docs/b0-41-readme-guidelines`. Avoid spaces, uppercase letters, vague names such as `changes`, and long-lived personal branches.

## 3. Create and update a branch

Start from an up-to-date `main`:

```bash
git switch main
git pull origin main
git switch -c docs/b0-41-readme-guidelines
```

Stage and commit only files related to the task:

```bash
git add README.md docs/branching-guidelines.md
git commit -m "docs: add project README and branching guidelines"
git push -u origin docs/b0-41-readme-guidelines
```

Replace the example branch name and file list with the ones relevant to your task.

## 4. Commit messages

Use a short imperative description and a conventional prefix:

- `feat:` new functionality
- `fix:` bug fix
- `docs:` documentation-only changes
- `test:` tests
- `refactor:` code restructuring without intended behavior changes
- `chore:` maintenance, configuration, or repository setup

Examples: `docs: explain local setup`, `feat: add booking search endpoint`.

Keep each commit focused. Avoid messages such as `updates`, `stuff`, or `final changes`.

## 5. Pull requests

Before opening a pull request:

1. Push your branch to GitHub.
2. Confirm the change is scoped to the Jira task and the branch is based on the current `main`.
3. Run the relevant tests, checks, or documentation review when available.
4. Open a pull request targeting `main`.
5. Include a concise summary, testing/check results, and the Jira issue key or link.
6. Request review from the relevant teammate(s), respond to feedback, and update the branch as needed.

Do not claim tests passed if they were not run. If no automated checks exist yet, state that clearly.

## 6. Merge and cleanup

- Merge only after required reviews and checks pass.
- Prefer the repository's configured merge strategy; keep the resulting history understandable.
- Delete the task branch after it has been merged, unless it is intentionally maintained.
- If work is not ready for review, mark the pull request as a draft.

## 7. Collaboration and safety

- Do not force-push shared branches or rewrite commits other teammates depend on.
- Do not commit access tokens, passwords, private keys, production data, or local `.env` files.
- Coordinate conflicting changes early and keep pull requests small enough to review.
- Keep the README and component documentation aligned with the actual project.
