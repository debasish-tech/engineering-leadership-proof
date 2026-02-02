# Engineering Metrics Scorecard

A framework for measuring engineering health and using metrics to drive decisions.

---

## Philosophy

You cannot improve what you do not measure. But measuring the wrong things is worse than measuring nothing.

Good engineering metrics are:
- **Leading indicators:** They predict problems before they become crises.
- **Actionable:** You can do something about them.
- **Resistant to gaming:** Improving the metric improves the actual outcome.

Bad engineering metrics are:
- **Vanity metrics:** They look good but do not connect to outcomes.
- **Lagging indicators:** They tell you what happened, but too late to act.
- **Easily gamed:** Teams can hit the metric without improving anything.

---

## The Scorecard

I track metrics across four categories: Velocity, Quality, Reliability, and Health.

### Sample Scorecard

| Category | Metric | Current | Target | Trend | Owner |
|---|---|---|---|---|---|
| **Velocity** | Deployment frequency | X/week | Y/week | Improving | [Name] |
| | Lead time (commit to production) | X days | Y days | Stable | [Name] |
| | Cycle time (start to done) | X days | Y days | Declining | [Name] |
| **Quality** | Escaped defects (production bugs) | X/month | Y/month | Improving | [Name] |
| | Test coverage (critical paths) | X% | Y% | Stable | [Name] |
| | Rollback rate | X% | Y% | Stable | [Name] |
| **Reliability** | Uptime (SLA) | X% | Y% | Stable | [Name] |
| | P0 incidents | X/month | Y/month | Improving | [Name] |
| | MTTR (mean time to recovery) | X min | Y min | Improving | [Name] |
| | MTTD (mean time to detect) | X min | Y min | Stable | [Name] |
| **Health** | On-call burden (pages/week) | X | Y | Declining | [Name] |
| | Engineering NPS (internal) | X | Y | Stable | [Name] |
| | Attrition (voluntary) | X% | Y% | Improving | [Name] |
| | Open headcount | X | Y | Stable | [Name] |

---

## Metric Definitions

### Velocity

**Deployment frequency:** How often we deploy to production. Higher is better, within reason.

**Lead time:** Time from code commit to running in production. Shorter is better.

**Cycle time:** Time from work starting to work done. Includes waiting time, not just active work.

### Quality

**Escaped defects:** Bugs that reach production and affect customers. Lower is better.

**Test coverage:** Percentage of critical paths covered by automated tests. Higher is better, but 100% is not the goal.

**Rollback rate:** Percentage of deployments that require rollback. Lower is better.

### Reliability

**Uptime:** Percentage of time the system is available. Target depends on SLA.

**P0 incidents:** Number of critical incidents per month. Lower is better.

**MTTR:** Mean time to recovery. How fast do we fix problems once detected?

**MTTD:** Mean time to detect. How fast do we notice problems?

### Health

**On-call burden:** Number of pages per on-call shift. High burden indicates product or process problems.

**Engineering NPS:** Internal satisfaction score. Do engineers recommend working here?

**Attrition:** Voluntary departure rate. High attrition is expensive and signals problems.

**Open headcount:** Positions we are trying to fill. Too many open positions slows teams down.

---

## How Leaders Use the Scorecard

### Monthly Review

Once a month, leadership reviews the scorecard together.

1. **Read the data.** What changed since last month?
2. **Identify trends.** What is improving? What is declining?
3. **Dig into red items.** Why is this metric below target?
4. **Decide on actions.** What are we going to do about it? Who owns it?
5. **Update the scorecard.** Record decisions and owners.

### Escalation Triggers

Some metrics should trigger immediate escalation:
- Uptime drops below SLA for more than [PLACEHOLDER: X] hours
- P0 incidents exceed [PLACEHOLDER: Y] in a month
- Attrition exceeds [PLACEHOLDER: Z%] in a quarter

These are not rules to follow blindly. They are signals that something needs attention.

### Avoiding Metric Abuse

Metrics can be gamed. Watch for these patterns:

**Cherry-picking:** Only reporting metrics that look good.
**Denominator manipulation:** Changing how you count to improve the ratio.
**Short-term optimization:** Hitting the metric this month at the expense of next quarter.
**Metric fixation:** Optimizing the metric instead of the underlying outcome.

The antidote is triangulation. Use multiple metrics that cross-check each other. If one metric improves dramatically while related metrics stay flat, investigate.

---

## Starting From Scratch

If you do not have metrics today, start simple:

**Week 1:** Pick 3 metrics. One from Velocity, one from Quality, one from Reliability.
**Week 2:** Figure out how to measure them. Automate if possible.
**Week 3:** Baseline. What are the current values?
**Week 4:** Set targets. What would "good" look like?
**Month 2:** Start the monthly review cadence.
**Quarter 2:** Add more metrics as you mature.

Do not try to measure everything at once. Start with what you can actually act on.

---

[Back to README](../README.md)
