# Triads

@Metadata {
  @PageImage(purpose: icon, source: "index-icon", alt: "CLIA icon")
  @PageImage(purpose: card, source: "index-card", alt: "CLIA card")
  @PageKind(article)
  @PageColor(blue)
}

Triads are CLIA’s **governance + execution** primitive: a small, explicit structure for describing *who* is acting, *what they’re responsible for*, and *what they’re doing next*.

In practice, a Triad binds three concepts together:

- **Agent** — the *actor* (a persona with capabilities and style).
- **Agency** — the *authority + constraints* (permissions, policies, boundaries, and operational context).
- **Agenda** — the *work plan* (priorities, next actions, and the sequence of moves).

## Why Triads exist

Most agent systems fail the same way: the “assistant” becomes a black box. Triads keep it legible.

- **Explicit roles**: separate the *persona* from the *permissions*.
- **Auditable decisions**: you can reason about what was allowed vs what was chosen.
- **Composable workflows**: agendas can be swapped without changing the agent’s identity.

## How it fits into CLIA

Triads sit between the CLI surface and the runtime:

**intent → triad selection/normalization → command execution → audit trail**

Triads also make collaboration easier: teams can share Agendas and Agencies while keeping Agents distinct.

## Where Triads live on disk (including public/private splits)

Triads are discovered under a repo’s `.clia/agents/<slug>/` directories.

If a workspace is split into visibility tiers (common in org monorepos), treat **`public/`** and **`private/`** as separate roots, each with its own `.clia/agents` tree.

Example layout:

- `public/.clia/agents/<slug>/<slug>@public.agent.triad.json`
- `public/.clia/agents/<slug>/<slug>@public.agency.triad.json`
- `public/.clia/agents/<slug>/<slug>@public.agenda.triad.json`
- `private/.clia/agents/<slug>/<slug>@private.agent.triad.json`
- `private/.clia/agents/<slug>/<slug>@private.agency.triad.json`
- `private/.clia/agents/<slug>/<slug>@private.agenda.triad.json`

Convention: the filename `@<dirTag>` should match the root (`public` or `private`) so there’s a single, unambiguous source of truth when both exist.
