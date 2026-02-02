# Execution vs Refactor: When to Pay Debt

A framework for deciding when to pay down technical debt and when to keep shipping.

---

## Context

Technical debt is not inherently bad. It is a tool. Taking on debt lets you move faster today in exchange for slower progress later. The question is not "should we have debt?" but "how much debt is appropriate, and when should we pay it down?"

Most orgs handle this poorly. They either ignore debt until it cripples them, or they refactor constantly and never ship. Neither approach works.

This framework helps you make conscious, defensible decisions about when to execute and when to refactor.

---

## Decision Criteria

### 1. Interest Rate
How much is this debt costing us right now?

High-interest debt is actively slowing down current work: every feature takes longer, incidents happen more frequently, engineers are frustrated. Pay this down soon.

Low-interest debt is not currently impacting velocity or reliability. It may become a problem later, but it is not urgent now.

### 2. Blast Radius
How much of the codebase or system does this debt affect?

- Localized debt (one module, one service): can often be paid opportunistically.
- Systemic debt (architecture, shared libraries, data models): requires dedicated investment.

### 3. Business Context
What else is competing for engineering time?

- Startup mode (product-market fit not yet achieved): lean toward execution. Speed matters more than perfection.
- Scale mode (proven product, growing fast): balance execution with foundation work. Debt becomes costlier.
- Maintenance mode (stable product, incremental growth): invest more in paying debt and reducing toil.

### 4. Team Morale
Is the debt making engineers miserable?

This is a real factor. High-morale teams ship faster. If a piece of debt is causing disproportionate frustration, paying it down may have ROI beyond the technical benefits.

### 5. Reversibility
Can we pay this debt incrementally, or does it require a big-bang rewrite?

- Incremental: lower risk, can stop if priorities change.
- Big-bang: higher risk, requires committed investment.

---

## Tradeoffs

| Choice | Upside | Downside |
|---|---|---|
| Execute (keep shipping) | Faster time to market, more features delivered | Debt compounds, velocity may slow over time |
| Refactor (pay debt) | Improved velocity later, better reliability, happier engineers | Opportunity cost of not shipping features |

---

## Anti-Patterns

**Debt denial.**
Pretending debt does not exist or refusing to track it. This leads to surprise slowdowns when the debt finally catches up.

**Goldplating.**
Refactoring things that are not actually causing problems. Perfect code that no one maintains is wasted effort.

**Big-bang rewrites without milestones.**
Starting a major refactor with no intermediate deliverables. These projects tend to drag on and often get canceled.

**Debt as blame.**
Using debt discussions to criticize past decisions or individuals. Debt is often a reasonable choice at the time. Focus on what to do now, not who to blame.

**Ignoring interest.**
Keeping debt that is actively costing you. If a piece of debt makes every sprint harder, you are paying interest every week. That adds up fast.

---

## Failure Modes

**The death spiral.**
You ignore debt for too long. Velocity drops. Leadership demands more features. The team skips more quality work to hit deadlines. Debt grows. Velocity drops further. Eventually, you cannot ship anything without breaking something else.

**The endless refactor.**
You start paying debt but never finish. Each refactor uncovers more debt. Engineers get frustrated. Business loses patience. The project gets canceled, and you are left with a half-refactored system that is worse than before.

**The premature optimization.**
You refactor for scale you do not have yet. The code is beautiful, but the company runs out of money before it matters.

---

## Example Scenario

**Situation:**
A platform team owns a data pipeline that ingests events from multiple sources. The pipeline was built quickly 18 months ago and has accumulated significant debt:
- No schema validation (causes downstream failures)
- Monolithic codebase (hard to test, deploy takes 45 minutes)
- No observability (debugging requires log diving)

Current state: pipeline handles [PLACEHOLDER: X] events/day. Business wants to add 3 new data sources in the next quarter.

**Analysis:**

| Dimension | Assessment |
|---|---|
| Interest rate | High. Every new integration takes 3x longer than it should. Incidents are frequent. |
| Blast radius | Systemic. The pipeline touches everything downstream. |
| Business context | Scale mode. Product is proven, growth is accelerating. |
| Team morale | Low. Engineers avoid working on the pipeline. |
| Reversibility | Incremental paydown is possible with careful sequencing. |

**Decision:**
Allocate [PLACEHOLDER: Y%] of team capacity to debt paydown over 2 quarters. Sequence the work:
1. Add observability first (reduces incident pain, helps with later work)
2. Add schema validation (prevents new failures)
3. Break apart the monolith incrementally (improve deploy time and testability)

Do not stop feature work entirely. Interleave debt paydown with the new data source integrations.

**Success criteria:**
- Incident count reduced by [PLACEHOLDER: Z%]
- New integration time reduced from [PLACEHOLDER: A weeks] to [PLACEHOLDER: B weeks]
- Deploy time reduced from 45 minutes to under 15 minutes

---

[Back to README](../README.md)
