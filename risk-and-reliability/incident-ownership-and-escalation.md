# Incident Ownership and Escalation

How I structure incident response to ensure clear accountability and fast resolution.

---

## Philosophy

Incidents are inevitable. How you handle them determines whether they become crises or learning opportunities.

Good incident response has three properties:
1. **Clear ownership:** Someone is in charge. Always.
2. **Fast escalation:** Problems reach the right people quickly.
3. **Communication discipline:** Stakeholders know what is happening without having to ask.

---

## Roles During an Incident

### Incident Commander (IC)

The IC owns the incident from start to resolution. They do not necessarily fix the problem. They coordinate the people who do.

**Responsibilities:**
- Declare incident severity
- Assemble the response team
- Make decisions about remediation approach
- Communicate status to stakeholders
- Decide when the incident is resolved

**Authority:**
The IC has full authority during the incident. They can pull in any engineer, escalate to any level, and make calls about tradeoffs.

### Technical Lead

The engineer(s) doing the actual investigation and remediation.

**Responsibilities:**
- Diagnose the problem
- Implement the fix
- Communicate technical status to the IC

### Communications Lead (for major incidents)

Handles external and internal communications so the IC can focus on resolution.

**Responsibilities:**
- Draft and send status updates
- Field questions from stakeholders
- Update status pages and communication channels

---

## Severity Levels

| Level | Definition | Response Time | Escalation |
|---|---|---|---|
| P0 | Customer-facing outage, major revenue impact, data loss risk | Immediate | Page on-call, notify leadership within 15 min |
| P1 | Significant degradation, partial outage, affecting many customers | 15 min | Page on-call, notify leadership within 1 hour |
| P2 | Minor impact, affecting some customers, workaround exists | 1 hour | Notify on-call, handle during business hours |
| P3 | Minimal impact, internal only, can wait | Next business day | Create ticket, prioritize normally |

---

## On-Call Expectations

On-call engineers are the first responders. Here is what I expect:

**Availability:**
- Respond to pages within [PLACEHOLDER: X] minutes
- Have laptop and connectivity available during on-call shift
- Do not schedule activities that prevent response

**Authority:**
- On-call can escalate to anyone, including leadership
- On-call can make decisions to mitigate impact (rollback, disable feature, scale resources)

**Support:**
- On-call should not be miserable. If it is, the product has problems we need to fix.
- Limit on-call shifts to [PLACEHOLDER: Y] days per rotation
- Compensate fairly for after-hours work
- Track on-call burden and address high-frequency pages

---

## Escalation Path

### Level 1: On-Call Engineer
First responder. Diagnose and resolve if possible.

### Level 2: Team Lead or Senior Engineer
Escalate if:
- Problem is outside on-call expertise
- Resolution requires multiple systems or teams
- On-call has been working for 30+ minutes without progress

### Level 3: Engineering Manager
Escalate if:
- Incident is P0 or high-impact P1
- Need to coordinate across multiple teams
- Customer or executive communication is required

### Level 4: Director or VP
Escalate if:
- Major customer impact or revenue impact
- Media or legal risk
- Need to make tradeoff decisions with business implications

Escalation is not failure. It is getting the right resources on the problem.

---

## Communication During Incidents

### Internal Communication

**Channel:** Dedicated incident channel (Slack, etc.)
**Frequency:** Every [PLACEHOLDER: X] minutes during active incident
**Content:**
- What we know
- What we are doing
- When the next update will be

### External Communication (for customer-facing incidents)

**Owner:** Communications Lead or IC
**Channel:** Status page, email, support channels
**Content:**
- What is affected
- What we are doing
- When to expect resolution (if known)

**Rules:**
- Do not lie. If you do not know, say so.
- Do not over-promise. Under-promise and over-deliver.
- Acknowledge the impact. Customers are frustrated. Validate that.

### Leadership Communication

**Trigger:** All P0 and P1 incidents
**Format:** Brief summary in leadership channel within 15 minutes
**Content:**
- What is happening
- Who is on it
- When the next update will be

---

## After the Incident

### Immediate (within 24 hours)
- Confirm incident is fully resolved
- Document timeline and actions taken
- Schedule postmortem if P0 or P1

### Postmortem (within 1 week)
- See [Postmortems That Change Outcomes](./postmortems-that-change-outcomes.md)

### Follow-Up (tracked to completion)
- Action items from postmortem are assigned and tracked
- Review at team lead sync until complete

---

## Anti-Patterns

**The blame game.**
Focusing on who caused the incident instead of how to prevent it. This teaches people to hide mistakes.

**The hero culture.**
Celebrating the person who fixed the incident instead of asking why it happened. Heroes are expensive. Systems are scalable.

**The infinite postmortem backlog.**
Creating action items that never get done. Every unresolved action item is a bet that the incident will not recur.

**The silent escalation.**
Not telling leadership about a major incident because you are "handling it." Leadership should know. They can help.

---

[Back to README](../README.md)
