# CLIA Org

CLIA (**Command Line Intelligent Assistant**) is a local‑first, memory‑secure agent spawning engine — built to run a GitHub org like an operating system, and staffed by a roster with actual personality.

CLIA is the command line where:

- issues become incidents
- repos become workspaces
- and automation becomes a governed system (not a black box)

CLIA is also a **secure process execution engine** with **complete memory isolation** — so secrets never leak to tools.

Built on the broader ecosystem: [Swift Universal](https://swift-universal.github.io/documentation/swift-universal).

@Metadata {
    @PageKind(article)
    @PageColor(orange)
    @PageImage(purpose: icon, source: "clia-agents-wrapped-2025-icon.svg")
    @PageImage(purpose: card, source: "clia-agents-wrapped-2025-card.svg")
}

<!-- -->

## Getting Started

### Install `clia-agent-cli` (from source)

```bash
git clone https://github.com/clia-org/clia-agent-cli.git
cd clia-agent-cli
swift build
```

- More: <doc:wrapped-2025/getting-started>

## Architecture

How the system stays legible and safe while still moving fast:

- <doc:wrapped-2025/scope-of-work>
- <doc:wrapped-2025/claw-vs-clia>
- <doc:wrapped-2025/claw-meets-clia>
- <doc:architecture/triads>
- <doc:architecture/s-type-system>

## 2025 Wrapped

- <doc:wrapped-2025/overview>
- <doc:wrapped-2025/roster>
- <doc:wrapped-2025/stats>
- <doc:wrapped-2025/top-100-commits>
- <doc:wrapped-2025/the-lost-logs>

---

## Your Year in Stats

| Metric | Score | Analysis |
| :--- | :--- | :--- |
| **Directives Issued** | **$sync** | You really like reloading context. |
| **Schemas Upgraded** | **0.3 → 0.4** | The "Triad" era begins. |
| **Files Moved** | **∞** | The Great `.clia/` Migration of October. |
| **Incidents** | **Managed** | Patch closed loops faster than you opened them. |

### The "Oh No" Moment
*Remember when we renamed `SwiftShell` to `CommonShell` and broke the build for 3 days?*
We laughed. We cried. We added a `no-op` wrapper. Good times.

---

## The Eras

@Row {
    @Column {
        ### Q1–Q2: The "Mono" Era
        We lived in `code/mono`. We built `Trader`. We validated the "One Repo to Rule Them All" hypothesis.
    }
    
    @Column {
        ### Q3: The "Agent" Era
        `.clia/agents/` was born. We stopped writing TODOs and started writing **Mandates**. `Codex` woke up.
    }
    
    @Column {
        ### Q4: The "Triad" Era
        Schema 0.4.0. Agent, Agency, Agenda. JSON became our love language.
    }
}

---

## Key Moments Timeline

- <doc:wrapped-2025/key-moments-timeline>

## Topics

### Getting Started

- <doc:wrapped-2025/getting-started>

### Architecture

- <doc:wrapped-2025/scope-of-work>
- <doc:wrapped-2025/scale-over-time>
- <doc:wrapped-2025/pwd-performance>
- <doc:wrapped-2025/claw-vs-clia>
- <doc:architecture/triads>
- <doc:architecture/s-type-system>
- <doc:wrapped-2025/key-moments-timeline>

### 2025 Wrapped

- <doc:wrapped-2025/overview>
- <doc:wrapped-2025/roster>
- <doc:wrapped-2025/stats>
- <doc:wrapped-2025/top-100-commits>
- <doc:wrapped-2025/the-lost-logs>

---

## Thank You for Playing

2025 was the year the CLI woke up. 
**See you in 2026.**

@Links(visualStyle: list) {
    - <doc:wrapped-2025/top-100-commits>
    - <doc:wrapped-2025/the-lost-logs>
}
