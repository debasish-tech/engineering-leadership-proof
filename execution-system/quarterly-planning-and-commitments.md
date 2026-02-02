# Quarterly Planning and Commitments

How I run quarterly planning to create alignment without bureaucracy.

---

## Purpose

Quarterly planning connects company goals to team work. Done well, it creates clarity: everyone knows what matters, why it matters, and how their work contributes.

Done poorly, it becomes a ritual that consumes weeks and produces documents no one reads.

This document describes my approach to quarterly planning.

---

## Planning Cadence

**Week -3 to -2:** Leadership alignment
- Confirm company priorities for the quarter
- Identify cross-team dependencies
- Set capacity constraints (hiring, holidays, known leave)

**Week -1:** Team planning
- Teams draft their quarterly goals
- Teams identify risks and dependencies
- Managers review and challenge

**Week 0 (start of quarter):** Commitment review
- Cross-functional review of all commitments
- Dependency negotiation
- Final commitment lock

**Ongoing:** Weekly check-ins (see [Operating Cadence](./operating-cadence-weekly-monthly-quarterly.md))

---

## What a Good Quarterly Plan Contains

### 1. Outcomes, Not Outputs
Teams commit to outcomes (results) rather than outputs (deliverables).

| Bad | Good |
|---|---|
| "Ship the new checkout flow" | "Increase checkout conversion by X%" |
| "Launch observability dashboard" | "Reduce mean time to detect incidents by Y%" |
| "Complete 12 sprints of work" | "Deliver capability Z that enables [business outcome]" |

### 2. Prioritized Goals
No more than 3 to 5 goals per team. If everything is a priority, nothing is.

Each goal should have:
- Clear success criteria (measurable)
- Owner (one person, not a committee)
- Confidence level (high, medium, low)

### 3. Explicit Tradeoffs
What are we NOT doing this quarter? Teams should name the things they are deprioritizing so leadership can validate the tradeoffs.

### 4. Dependencies
What do we need from other teams? What do other teams need from us? Name the dependencies, agree on delivery dates, and escalate blockers early.

### 5. Risks
What could prevent us from hitting our goals? What is our mitigation plan?

---

## Commitment Levels

I use three levels of commitment:

**P0 (Must do):**
These are hard commitments. If we miss these, the quarter is a failure. Reserve P0 for goals that truly matter.

**P1 (Plan to do):**
These are stretch goals. We expect to complete them, but they can slip if P0 work takes longer than expected.

**P2 (Will do if time allows):**
Nice-to-haves. Do not plan for these. Only pick them up if P0 and P1 are on track.

Healthy ratio: 60% P0, 30% P1, 10% P2 buffer.

---

## Avoiding Planning Failure Modes

**The wish list.**
Teams list everything they want to do without capacity constraints. The plan is unrealistic from day one.

Fix: Force rank. If you can only do 3 things, which 3? Start there.

**The output factory.**
Teams commit to shipping features without connecting them to business outcomes.

Fix: Ask "so what?" for every commitment. If a feature ships, what changes?

**The dependency maze.**
Every team depends on every other team. No one can move without coordination.

Fix: Reduce dependencies. If a dependency is blocking, pull the work in-house or defer the goal.

**The unchanging plan.**
The plan is set at the start of the quarter and never revisited, even when circumstances change.

Fix: Review the plan monthly. Adjust commitments if the world changes. This is not failure; it is responsiveness.

**The vanity metrics.**
Teams commit to metrics they can game. The metric goes up, but nothing actually improves.

Fix: Choose metrics that matter to customers or the business. If you can hit the metric without improving outcomes, pick a different metric.

---

## Template

See [OKR Template](../templates/okr-template.md) for the format I use.

---

## How I Run the Commitment Review

The commitment review is a meeting where all engineering teams present their quarterly plans to each other and leadership.

**Format:**
- Each team gets [PLACEHOLDER: X] minutes to present
- Format: goals, success criteria, dependencies, risks
- Other teams ask clarifying questions
- Leadership validates tradeoffs
- Dependencies are negotiated in real time or assigned follow-up owners

**Rules:**
- No new goals in the meeting. Present what you planned, not what you invented that morning.
- Challenge constructively. The goal is clarity, not gotcha questions.
- Decisions in the room. Do not defer everything to follow-up.

**Output:**
A shared document with all team commitments, dependencies, and risks. This becomes the source of truth for the quarter.

---

[Back to README](../README.md)
