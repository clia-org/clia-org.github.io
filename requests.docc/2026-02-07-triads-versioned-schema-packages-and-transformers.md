# 2026-02-07 — Triads versioned schema packages + generic transformers

## Status

Proposed (feature request).

## Context

Triads advanced from `0.4.0` to `0.5.0` (adds `restrictions`). We want to:

- load and validate older triad versions automatically
- define explicit, reusable transformation operations (upgrade/normalize)
- avoid SwiftPM’s single-version-per-package constraint by making schema versions distinct package identities

## Goals

1) **Versioned schema packages**: Each triads schema version is shipped as its own SPM package.
2) **Generic transformation ops**: Define standard upgrade/normalize steps and apply them consistently.
3) **Backward compatibility**: The CLI should read older triads and upgrade in-memory to current types.
4) **Explicit writeback**: Never rewrite files unless the user explicitly requests it.

## Non-Goals

- Automatically tagging/cutting releases.
- Supporting unlimited historical versions forever.

## Proposed Packaging

For each triads schema version, publish a package with a fixed-width version code:

- Package naming: `CLIAOrgTriadSchemaV<NNNNNNNN>`
  - 2 digits major, 2 digits minor, 4 digits revision
  - Example mappings:
    - `0.4.0` → `CLIAOrgTriadSchemaV00040000`
    - `0.5.0` → `CLIAOrgTriadSchemaV00050000`

Each package exports bundled resources:

- `.clia/schemas/triads/triads.core.json`
- `.clia/schemas/triads/triads.agent.schema.json`
- `.clia/schemas/triads/triads.agenda.schema.json`
- `.clia/schemas/triads/triads.agency.schema.json`

`clia-agent-cli` depends on a configured set of schema packages (at least current + previous), and selects the correct schema bundle by `schemaVersion`.

## Proposed Transformations (Generic Ops)

Define a small set of standard operations with well-defined semantics:

### 1) `validate`
- Input: JSON document + schema version + kind (agent/agenda/agency)
- Output: pass/fail + diagnostics

### 2) `upgrade` (in-memory)
- Input: decoded older-version doc
- Output: current-version doc in-memory
- Must be deterministic and side-effect-free.

### 3) `normalize` (current-version canonicalization)
- Input: current-version doc
- Output: current-version doc with canonical formatting and field moves
  - e.g. `extensions.x-emoji` → `emoji`
  - e.g. `extensions.x-restrictions` → `restrictions`

### 4) `rewrite` (explicit)
- Input: file path(s)
- Behavior: read → validate → upgrade → normalize → write back
- Requires explicit user invocation and supports `--dry-run`.

### 5) `diff`
- Show a stable semantic diff between original and upgraded+normalized output.

## Compatibility Policy

- Support reading the last **N** schema versions (recommended N=2 initially).
- Writing always targets `TriadSchemaVersion.current`.

## Acceptance Criteria

- [ ] New schema packages exist for `0.4.0` and `0.5.0`.
- [ ] `clia-agent-cli` can load the correct schema bundle for a given file’s `schemaVersion`.
- [ ] `clia triads validate` validates against the file’s declared schema version.
- [ ] `clia triads upgrade --dry-run` reports planned changes.
- [ ] `clia triads rewrite` writes only when explicitly requested.

## Open Questions

- Where to encode the version mapping (`0.4.0` → `00040000`): hardcoded table vs parser.
- Whether triads `schemaVersion` should remain semver-ish (`0.5.0`) or move to fixed-width code.
- How to handle unknown versions: error vs best-effort fallback.
