# OpenClaw vs CLIA

OpenClaw and CLIA are complementary. They overlap in “agent” vocabulary, but they solve different layers of the system.

## One sentence each

- **CLIA**: the **agentic architecture** (governance + models + command sets) for running an autonomous GitHub org.
- **OpenClaw**: the **operational host** (runtime + integrations) that routes messages, runs tools, and keeps agents alive in the real world.

## What CLIA owns

CLIA is the *system design* and the *contract*.

- **Triads** (Agent / Agency / Agenda)
- **S‑Type** operating posture (how an agent behaves)
- **Core models** and reusable command sets
- **Normalization + audits** (make behavior legible and repeatable)

If you want to answer: “What is this org? How does it stay safe? What are the primitives?” — that’s CLIA.

## What OpenClaw owns

OpenClaw is the *execution environment*.

- Channel ingress/egress (Discord, etc.)
- Tool execution (filesystem, git, browser, nodes)
- Background sessions, cron/reminders
- Message routing and delivery guarantees

If you want to answer: “How does the agent actually run continuously, talk in channels, and use tools?” — that’s OpenClaw.

## How they fit together

**CLIA defines the rules. OpenClaw runs the game.**

Typical flow:

1) A human issues intent in a channel.
2) OpenClaw receives the message and invokes the agent.
3) The agent uses CLIA concepts (Triads/S‑Type) to choose posture + next actions.
4) OpenClaw executes tools and delivers outputs.
5) CLIA audit/structure keeps the run understandable.

## Practical guidance

- When writing docs about *governance and system structure*: link **CLIA** topics.
- When writing docs about *runtime behavior and integrations*: link **OpenClaw** docs.

## Topics

### Claw vs CLIA

- <doc:claw-vs-clia-development>

### CLIA Architecture

- <doc:triads>
- <doc:s-type-system>
