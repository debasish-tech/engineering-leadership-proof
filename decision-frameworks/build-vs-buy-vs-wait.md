# Build vs Buy vs Wait

A framework for deciding whether to build internally, buy a solution, or delay the decision.

---

## Context

Every engineering leader faces this decision regularly. Should we build it ourselves, buy an existing solution, or wait until we have more information? The wrong choice wastes time, money, and team morale.

Most orgs default to one approach. Build-first orgs over-invest in custom solutions. Buy-first orgs accumulate vendor sprawl. Wait-first orgs miss opportunities.

The right answer depends on context. This framework helps clarify that context.

---

## Decision Criteria

Evaluate across these five dimensions:

### 1. Strategic Differentiation
Does this capability create competitive advantage?

- If yes: lean toward build. Core differentiators should not depend on vendor roadmaps.
- If no: lean toward buy. Do not build commodity infrastructure.

### 2. Time to Value
How quickly do we need this capability?

- Urgent (weeks): buy or wait. Building takes longer than most teams admit.
- Moderate (quarters): evaluate build vs buy honestly.
- Long-term (years): build may be viable if the capability is strategic.

### 3. Total Cost of Ownership
What is the full cost over 3 to 5 years?

Build costs include: initial development, ongoing maintenance, hiring and retention, opportunity cost of engineers not working on other things.

Buy costs include: licensing fees, integration work, vendor lock-in, feature gaps that require workarounds.

Most teams underestimate build costs by 2x to 3x.

### 4. Team Capability
Do we have the expertise to build and maintain this?

- If yes: build is viable.
- If no: buying or waiting while you build expertise is smarter than building poorly.

### 5. Reversibility
How hard is it to change course later?

- Highly reversible: make a fast decision either way.
- Difficult to reverse: invest more time in evaluation before committing.

---

## Tradeoffs

| Choice | Upside | Downside |
|---|---|---|
| Build | Full control, no vendor dependency, tailored to your needs | Longer time to value, ongoing maintenance burden, opportunity cost |
| Buy | Faster time to value, external expertise, predictable cost | Vendor lock-in, feature gaps, integration complexity |
| Wait | Preserve optionality, learn from market, avoid premature investment | Opportunity cost of delay, competitors may move faster |

---

## Anti-Patterns

**"Not Invented Here" syndrome.**
Refusing to buy because "we can build it better" when the capability is not a differentiator and the team is already stretched.

**Vendor capture.**
Buying without negotiating exit clauses or understanding lock-in. Every vendor wants you dependent on them.

**Analysis paralysis.**
Waiting indefinitely because the decision is hard. At some point, making a reversible decision and learning is better than continued analysis.

**Underestimating maintenance.**
Building something and assuming it will run itself. Every system requires ongoing investment. Budget for it or do not build.

**Ignoring integration costs.**
Buying a tool but not accounting for the engineering time to integrate it. Integration is often 50% or more of the total cost.

---

## Failure Modes

**Building a solved problem.**
You spend 6 months building something that a mature vendor does better for a reasonable price. Your engineers are demoralized, and you still have to maintain it.

**Buying and regretting.**
You buy a tool that does 80% of what you need. The missing 20% requires workarounds that consume more engineering time than building would have.

**Waiting until it is too late.**
You delay the decision, and a competitor ships a feature that requires this capability. Now you are playing catch-up under pressure.

---

## Example Scenario

**Situation:**
A Series C SaaS company needs an internal developer platform for CI/CD, environments, and observability. The current setup is a patchwork of scripts and manual processes.

**Analysis:**

| Dimension | Assessment |
|---|---|
| Strategic differentiation | Low. CI/CD is not a competitive differentiator for this company. |
| Time to value | Moderate. Need something in 2 quarters. |
| Total cost | Build estimate: 18 engineer-months + ongoing maintenance. Buy estimate: [PLACEHOLDER: $X/year] licensing + 4 engineer-months integration. |
| Team capability | Limited platform engineering expertise on staff. |
| Reversibility | Medium. Either choice creates some lock-in. |

**Decision:**
Buy a platform solution, but negotiate a 12-month contract with exit terms. Use the saved engineering time to focus on product features that are actual differentiators.

**Follow-up:**
Re-evaluate in 12 months. If the vendor is not meeting needs, revisit the build option with a better-informed perspective.

---

[Back to README](../README.md)
