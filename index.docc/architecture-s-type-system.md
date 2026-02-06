# The S-Type System

@Metadata {
  @PageImage(purpose: icon, source: "index-icon", alt: "CLIA icon")
  @PageImage(purpose: card, source: "index-card", alt: "CLIA card")
  @PageKind(article)
  @PageColor(blue)
}

The S-Type system is CLIA's shorthand for **behavioral modes**-a lightweight way to describe *how* an agent should operate (not just what it should do).

It's used to tune things like:

- decision speed vs deliberation
- verbosity vs terseness
- risk tolerance (e.g., safe read-only defaults)
- how aggressively the agent proposes/executes changes

## Why it matters

Agents aren't one-size-fits-all. The same person might want:

- a careful, reversible "safety-first" operator for production
- a fast, creative "draft-and-iterate" mode for writing
- a strict, methodical "systems steward" for repo hygiene

S-Type provides a common vocabulary for those modes so:

- humans can request a mode quickly ("run this in a careful S-Type")
- tools can enforce guardrails (e.g., no destructive actions)
- teams can standardize expectations across agents

## How it connects to Triads

S-Type is typically expressed through the **Agency** (constraints and operating posture) and reinforced by the **Agenda** (what is allowed and what is next).

Think of it as: **Triad = who/what/next**, **S-Type = how**.
