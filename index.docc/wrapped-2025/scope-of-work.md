# Scope of Work

CLIA’s “autonomous GitHub org” story only makes sense when you can see the surface area.
This page is a map of the repos, packages, and documentation that make up the system.

## 🗺️ The repo constellation

### 🧰 Core workspaces

| Repo | What it is | Why it matters |
| :--- | :--- | :--- |
| **todo3** | Operational workspace (agents, incidents, logs, orchestration) | Where the org *actually runs* |
| **mono** | Monorepo hub hosting org subtrees (DocC + SPM + foundations) | Shared surface area + reuse |

### 📚 Public documentation sites (DocC)

| Site | Purpose |
| :--- | :--- |
| **clia-org.github.io** | CLIA public docs |
| **swift-universal.github.io** | Swift Universal docs |
| **wrkstrm.github.io** | Wrkstrm docs |
| **codeswiftly.github.io** | CodeSwiftly docs |
| **laussat-studio.github.io** | Studio Laussat docs |

### 🧠 Runtime + execution host

- **openclaw** — operational host/runtime (tool execution, message routing, background runs)

## 🧱 Libraries and packages (selected)

These are the reusable building blocks that make the system real.

### 🧊 Swift Universal (system foundations)

| Package | What it does |
| :--- | :--- |
| `common-process` | process execution |
| `common-shell` | shell ergonomics + scripting helpers |
| `common-cli` | CLI primitives |
| `common-log` | logging |

### 🛠️ Wrkstrm / Tooling (developer surface)

| Package | What it does |
| :--- | :--- |
| `any-language-model` | model abstraction layer |
| `swift-cli-kit` | CLIs as composable building blocks |
| `configs` | shared configs (linting/workflows/tool defaults) |
| `swift-figlet-kit` | ASCII/figlet rendering |
| `wrkstrm-*` | foundational system libraries (foundation/main/networking/perf/color/emoji) |

## 📈 Scale (repo stats)

A rough view of the surface area inside the `mono` workspace (counted from the repo tree):

| Metric | Count | How it was counted |
| :--- | ---: | :--- |
| Swift source files | ~11,656 | `orgs/**/Sources/**/*.swift` |
| Swift test files | ~5,770 | `orgs/**/Tests/**/*.swift` |
| Text/config artifacts | ~36,882 | `*.swift`, `*.md`, `*.yml|yaml`, `*.json` under `orgs/` |

These numbers are intentionally coarse — they’re here to communicate scope, not precision.

## What this represents

- **Code**: executable tools + libraries (SPM), plus runtime infrastructure.
- **Docs**: multiple DocC sites published as GitHub Pages.
- **Operations**: a local-first workflow with auditable structure (Triads / S‑Type / incidents).

If you want a specific repo list with URLs for every component above, we can expand this into a full index.
