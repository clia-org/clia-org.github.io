# Scope of Work

CLIA’s “autonomous GitHub org” story only makes sense when you can see the surface area.
This page is a map of the repos, packages, and documentation that make up the system.

## The repo constellation

### Core workspaces

- **todo3** — the day‑to‑day operational workspace (agents, incidents, logs, orchestration).
- **mono** — the shared monorepo hub that hosts org subtrees (DocC sites, SPM packages, and shared foundations).

### Public documentation sites (DocC)

- **clia-org.github.io** — CLIA’s public docs site.
- **swift-universal.github.io** — Swift Universal public docs.
- **wrkstrm.github.io** — Wrkstrm public docs.
- **codeswiftly.github.io** — CodeSwiftly public docs.
- **laussat-studio.github.io** — Studio Laussat public docs.

### Runtime + execution host

- **openclaw** — the operational host/runtime that executes tools, routes messages, and keeps agents alive.

## Libraries and packages (selected)

These are the reusable building blocks that make the system real:

### Swift Universal

- `common-process`
- `common-shell`
- `common-cli`
- `common-log`

### Wrkstrm / Tooling

- `any-language-model`
- `swift-cli-kit`
- `configs`
- `swift-figlet-kit`
- `wrkstrm-foundation`, `wrkstrm-main`, `wrkstrm-networking`, `wrkstrm-performance`, `wrkstrm-color`, `wrkstrm-emoji`

## What this represents

- **Code**: executable tools + libraries (SPM), plus runtime infrastructure.
- **Docs**: multiple DocC sites published as GitHub Pages.
- **Operations**: a local-first workflow with auditable structure (Triads / S‑Type / incidents).

If you want a specific repo list with URLs for every component above, we can expand this into a full index.
