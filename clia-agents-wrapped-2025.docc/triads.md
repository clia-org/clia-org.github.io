# Triads

Triads are CLIA’s **governance + execution** primitive: a small, explicit structure for describing *who* is acting, *what they’re responsible for*, and *what they’re doing next*.

A Triad binds three concepts:

- **Agent** — the actor (persona + capabilities).
- **Agency** — authority + constraints (permissions, policies, boundaries, operating posture).
- **Agenda** — the plan (priorities and next actions).

## Why it exists

Most agent systems fail the same way: the assistant becomes a black box.
Triads keep the system legible:

- **Role clarity**: separate persona from permission.
- **Auditable behavior**: distinguish what was *allowed* from what was *chosen*.
- **Composable workflows**: swap agendas/agencies without rewriting the agent.

## Where it fits

**intent → triad selection/normalization → command execution → audit trail**
