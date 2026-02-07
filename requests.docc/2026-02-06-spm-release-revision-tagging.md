# 2026-02-06 — SPM release revision tagging + post-commit revision bump

## Status

Proposed (feature request).

## Goal

Operationalize SwiftPM package releases (which are versioned via git tags) so we:

- consistently tag releases when package code changes
- have a monotonically increasing **revision marker** in each repo/submodule to aid traceability
- can automate “what needs a release” detection without relying on human memory

## Non-Goals

- Automatically create release tags in `post-commit` (too easy to mis-tag partial work).
- Replace semver tags as the canonical SwiftPM release signal.

## Proposed Approach

### 0) Submodule + SwiftPM package release procedure (resolve → commit → tag → bump superproject)

When the upstream is a **git submodule** that contains a **SwiftPM package**, tagging must happen on a commit where SwiftPM has been resolved.

Procedure (happy path):

1) Superproject clean.
2) Update submodule to the target branch head (`main` or release branch).
3) In the submodule, run `swift package resolve` for the package root.
4) If `Package.resolved` is tracked and changed: commit it **in the submodule**.
5) (Optional but recommended) run `swift test`.
6) Tag the submodule HEAD (annotated tag) and push the tag.
7) In the superproject, checkout the submodule to that tag and commit the submodule pointer bump.

Why this ordering:
- SwiftPM tags should refer to a commit whose dependency resolution is deterministic.
- The superproject submodule SHA should point at an immutable, named release.

### A) Repo revision marker (post-commit hook)

Introduce a lightweight post-commit hook that, after a successful commit, bumps a canonical revision marker in any repo/submodule that had changes committed.

- Canonical file: `REVISION` (or `.clia/revision`) at repo root.
- Format: integer (monotonic).
- Behavior:
  - bump once per commit per repo
  - never bump if the commit only changes the revision file itself
  - stage + create a follow-up commit automatically (or instruct the user to run a follow-up command)

### B) Release intent gating (CI)

Add CI that requires explicit release intent when package-relevant files change.

Examples of intent signals:
- PR label: `release:patch|minor|major`
- or entry in `releases/next.md`

### C) Release tagging command

Provide a single command to cut and push a SwiftPM-compatible tag for a given package.

- Validates clean tree, on main, tests pass
- Chooses next version based on explicit input or release intent
- Creates annotated tag and pushes it

## Acceptance Criteria

- [ ] A documented, one-command install step for hooks.
- [ ] Post-commit hook increments repo revision marker reliably.
- [ ] CI can detect package changes and require release intent.
- [ ] A release command exists that creates the correct git tag(s) for SwiftPM.

## Open Questions

- Tag naming scheme: `clia-agent-cli@X.Y.Z` vs `X.Y.Z`.
- Scope: mono-wide tags vs per-package tags.
- Where should the canonical revision marker live: `REVISION` vs `.clia/revision`.
