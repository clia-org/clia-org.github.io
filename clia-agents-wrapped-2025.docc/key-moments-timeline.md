# Key Moments Timeline

A few anchor points from the year — the moments where the system *changed shape*.

## 2025 (high level)

- **Q1–Q2: The “Mono” era** — consolidated work into `code/mono` and validated the single-repo hypothesis.
- **Q3: The “Agent” era** — formalized agents, mandates, and operational routines.
- **Q4: The “Triad” era** — Schema 0.4.0: Agent / Agency / Agenda became the governing structure.

## 🧭 Notable moments (dated)

| Window | Who | What happened | Why it mattered |
| :--- | :--- | :--- | :--- |
| **Apr–Jun 2025** | rismay | Tried options trading software built on JavaScript (single-threaded). Lost too much money due to **memory leaks**. | A hard lesson in reliability: correctness + memory safety aren’t “nice to have” when money is on the line. |
| **Jul–Sep 2025** | rismay | Began work on **Tau** to trade options programmatically. Started a **secure secret service** (macOS native + Linux compatible). Needed a **daemon** to run 24/7 for trading. | Forced the architecture to treat secrets + long-running execution as first-class concerns. |
| **Jul 2025** | Codex / CLIA | **Codex CLI** debuts; CLIA development is **elevated to that level**. | Codex became the stable “platform level” that CLIA rose to meet — the bridge before OpenClaw. |

## Other moments

- The **CommonShell** transition (and the 3‑day build break) — the lesson: keep compatibility shims until consumers migrate.
- The **Great `.clia/` migration** — structure won over sprawl.
