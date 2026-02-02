# Platform Team Models

A framework for organizing platform teams that serve internal engineering customers effectively.

---

## Context

Platform teams exist to make product teams more productive. They build and maintain shared infrastructure: CI/CD, developer environments, observability, data platforms, internal tools.

Done well, platform teams are force multipliers. Done poorly, they become bottlenecks that slow everyone down.

This document describes the models I have used to organize platform teams and when each model works best.

---

## Models

### Model 1: Embedded Platform Engineers

Platform engineers sit within product teams rather than in a separate org.

**How it works:**
Each product team has one or more engineers who focus on infrastructure, tooling, and operational concerns. They report to the product team lead but coordinate with a platform guild or working group.

**Best for:**
- Early-stage companies (under 30 engineers)
- Organizations with strong product team autonomy
- Situations where platform needs vary significantly across teams

**Tradeoffs:**
- Pros: fast iteration, tight product alignment, no cross-team dependencies
- Cons: duplicated effort, inconsistent tooling, hard to share learnings

### Model 2: Central Platform Team

A dedicated team owns all shared platform capabilities.

**How it works:**
One team builds and maintains CI/CD, environments, observability, and internal tools. Product teams consume these as services. Platform team sets standards and provides support.

**Best for:**
- Mid-size companies (30 to 150 engineers)
- Organizations that need consistency across teams
- Situations where platform investment is a priority

**Tradeoffs:**
- Pros: consistency, specialization, economies of scale
- Cons: can become a bottleneck, may lose touch with product team needs

### Model 3: Platform as a Product

The platform team operates like an internal product team, with product managers, roadmaps, and customers (other engineering teams).

**How it works:**
Platform team has its own PM who talks to internal customers (product teams), prioritizes work, and measures success by customer satisfaction and adoption. Platform team ships capabilities that product teams choose to adopt.

**Best for:**
- Larger organizations (150+ engineers)
- Companies where platform adoption should be voluntary, not mandated
- Situations where platform team needs to earn trust

**Tradeoffs:**
- Pros: customer focus, clear prioritization, reduces mandated adoption friction
- Cons: requires PM investment, slower to achieve consistency, some teams may not adopt

### Model 4: Hybrid (Hub and Spokes)

Combines central platform team with embedded platform engineers in product teams.

**How it works:**
A central platform team owns core infrastructure and sets standards. Embedded engineers in product teams customize and extend the platform for their specific needs. Regular sync between central and embedded engineers.

**Best for:**
- Large, diverse organizations
- Companies with varying product team needs
- Situations requiring both consistency and flexibility

**Tradeoffs:**
- Pros: balances consistency and autonomy, scales better, knowledge sharing
- Cons: coordination overhead, potential for tension between central and embedded

---

## Decision Criteria

| Factor | Favors Central | Favors Embedded | Favors Hybrid |
|---|---|---|---|
| Org size | 30-150 engineers | Under 30 engineers | Over 150 engineers |
| Team autonomy | Low autonomy culture | High autonomy culture | Mixed |
| Platform maturity | Mature, stable needs | Rapidly evolving needs | Varied by team |
| Consistency need | High (compliance, security) | Low (experimentation) | Moderate |

---

## Anti-Patterns

**The ivory tower.**
Platform team builds what they think is cool, not what product teams need. Adoption is mandated rather than earned. Product teams resent the platform team.

**The ticket queue.**
Platform team becomes a service desk. Product teams file tickets. Platform team works the queue. No proactive improvement happens. Everyone is frustrated.

**The shadow platform.**
Product teams do not trust the central platform, so they build their own tooling in secret. Now you have multiple platforms to maintain, and none of them are good.

**The infinite scope.**
Platform team tries to own everything. They become spread too thin. Nothing gets done well.

**The missing feedback loop.**
Platform team ships capabilities but does not measure adoption or satisfaction. They have no idea if they are succeeding.

---

## Failure Modes

**Bottleneck at scale.**
Central platform team cannot keep up with demand. Product teams are blocked waiting for platform work. Frustration builds. People start working around the platform.

**Inconsistency chaos.**
Embedded model with no coordination. Every team has different tooling. Onboarding is painful. Knowledge does not transfer. Incidents are harder to debug.

**Adoption failure.**
Platform team ships a capability, but no one uses it. The team is demoralized. Leadership questions the investment.

---

## Example Scenario

**Situation:**
A Series C company has grown from 40 to 120 engineers over 18 months. They started with the embedded model. Now they have:
- 4 different CI/CD setups across teams
- No standard observability
- Inconsistent deployment practices
- Frequent "works on my machine" problems

**Analysis:**

| Factor | Assessment |
|---|---|
| Org size | 120 engineers, entering the range where central makes sense |
| Team autonomy | Historically high, but causing coordination problems |
| Platform maturity | Low. Need to establish foundations. |
| Consistency need | Growing. Compliance requirements increasing. |

**Decision:**
Move to a hybrid model:
1. Form a central platform team (5 engineers, 1 PM)
2. Define "paved path" standards for CI/CD, observability, and deployment
3. Keep one embedded platform engineer in each major product area
4. Central team builds the core platform. Embedded engineers adapt it to team needs.
5. Measure adoption quarterly. Do not mandate, but make the paved path clearly better than alternatives.

**Success criteria:**
- [PLACEHOLDER: X%] of teams on the standard CI/CD within 6 months
- Deploy time reduced from [PLACEHOLDER: Y minutes] to [PLACEHOLDER: Z minutes]
- "Works on my machine" incidents reduced by [PLACEHOLDER: A%]
- Platform team NPS (internal customer satisfaction) above [PLACEHOLDER: B]

---

[Back to README](../README.md)
