# Org Design Patterns at Scale

How I structure engineering organizations as they grow.

---

## Philosophy

Org structure is a tool, not a goal. The right structure depends on your strategy, your people, and your stage. There is no universal answer.

That said, patterns exist. This document describes the patterns I have used and when each works best.

---

## Core Principles

### Small Teams with Clear Ownership

Teams should be small enough that everyone knows each other (typically 5 to 8 people) and have clear ownership of outcomes.

Why small? Communication overhead scales with team size. A team of 10 has 45 communication paths. A team of 6 has 15.

Why clear ownership? Diffuse ownership means no one is accountable. If everyone owns something, no one owns it.

### Minimize Dependencies

The more teams depend on each other, the slower everyone moves. Design team boundaries to minimize cross-team dependencies.

Where dependencies are unavoidable, make them explicit. Define interfaces. Negotiate SLAs.

### Align to Value Streams

Organize teams around delivering value to customers or the business, not around technical components.

A team that owns a feature end-to-end (frontend, backend, data) can move faster than a team that has to coordinate with three other teams for every change.

### Flexibility Over Rigidity

Org structures need to evolve. Do not over-invest in a structure that will change in 6 months. Make changes when needed, not as a last resort.

---

## Team Structures

### Feature Teams (Cross-Functional)

Teams organized around customer-facing features or product areas.

**Composition:** Engineers across the stack (frontend, backend, sometimes data), often with embedded product and design.

**Ownership:** Full ownership of a product area. Can ship features independently.

**Best for:**
- Product-focused companies
- When speed of feature delivery matters most
- When product areas are relatively independent

**Challenges:**
- Potential code duplication across teams
- May underinvest in shared infrastructure
- Requires strong product definition

### Component Teams (Technical)

Teams organized around technical components (API, database, mobile app, etc.).

**Composition:** Engineers with deep expertise in a specific technology or layer.

**Ownership:** Owns a technical component that multiple product areas use.

**Best for:**
- When components are truly shared and complex
- When deep technical expertise is needed
- Early-stage companies with small engineering teams

**Challenges:**
- Features require coordination across multiple teams
- Slower feature delivery
- Teams may optimize for their component, not the customer

### Platform Teams

Teams that provide capabilities to other engineering teams.

**Composition:** Engineers focused on infrastructure, tooling, and developer experience.

**Ownership:** Owns shared platforms (CI/CD, observability, cloud infrastructure) and serves internal customers.

**Best for:**
- Mid-size to large engineering orgs
- When platform capabilities are a bottleneck
- When consistency across teams matters

**Challenges:**
- Can become a bottleneck if not run well
- May lose touch with product team needs
- Requires PM mindset (treat internal teams as customers)

See [Platform Team Models](../decision-frameworks/platform-team-models.md) for more detail.

---

## Scaling the Org

### 10 to 30 Engineers

**Pattern:** Flat structure with senior engineers leading areas informally.

**Management:** One or two engineering managers. Leaders are player-coaches.

**Coordination:** Direct communication. Weekly all-hands. No formal process needed.

### 30 to 100 Engineers

**Pattern:** Team structure emerges. 5 to 10 teams with clear ownership.

**Management:** Team leads or managers for each team. Director-level leader for the org.

**Coordination:** Team lead syncs. Quarterly planning. Dependency negotiation.

### 100 to 300 Engineers

**Pattern:** Teams grouped into areas (pods, pillars, verticals). Platform teams formalized.

**Management:** Managers of managers. VP or Senior Director leading the org.

**Coordination:** Operating cadence (see [Operating Cadence](../execution-system/operating-cadence-weekly-monthly-quarterly.md)). Cross-team rituals. More formal planning.

### 300+ Engineers

**Pattern:** Multiple org units, each with its own structure. Possible geographic distribution.

**Management:** VPs for major areas. Clear succession planning.

**Coordination:** Formal operating model. Executive-level alignment. Heavy investment in communication.

---

## Reporting Structures

### Manager Span of Control

Ideal: 5 to 8 direct reports for line managers. Can stretch to 10 for experienced managers with independent reports.

Too few: Manager is a bottleneck. Reports do not get enough attention.
Too many: Manager cannot provide adequate support. 1:1s become infrequent.

### Tech Lead vs Manager

Some orgs separate technical leadership (Tech Lead) from people management (Engineering Manager).

**Combined (Tech Lead Manager):**
- One person owns both technical direction and team health
- Works well for smaller teams or strong individual contributors growing into leadership
- Risk: excellent IC becomes mediocre manager

**Split (Tech Lead + Engineering Manager):**
- Tech Lead owns architecture, technical quality, and delivery
- Engineering Manager owns people: hiring, growth, performance
- Works well for larger teams or when technical complexity is high
- Risk: unclear accountability, coordination overhead

I have used both. The key is clear role definition and strong partnership between the two roles.

---

## Reorgs

Reorgs are expensive. They disrupt relationships, change ownership, and create uncertainty. Do not reorg casually.

**Good reasons to reorg:**
- Strategy changed and the current structure does not support it
- Teams are too big or too small
- Ownership is unclear or fragmented
- Dependencies are creating unacceptable slowdowns

**Bad reasons to reorg:**
- New leader wants to "put their stamp" on things
- Avoiding a hard conversation with an underperforming leader
- Cargo-culting what another company does

**How I run reorgs:**
1. Define the goal. What problem are we solving?
2. Design options. Consider multiple structures.
3. Evaluate tradeoffs. Every structure has downsides. What can we live with?
4. Communicate clearly. Explain the why, the what, and the how.
5. Execute quickly. Long transitions are painful.
6. Follow up. Check if the reorg achieved its goals after [PLACEHOLDER: X] months.

---

[Back to README](../README.md)
