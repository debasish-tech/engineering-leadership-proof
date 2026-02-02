# Postmortems That Change Outcomes

How to run postmortems that actually prevent repeat incidents.

---

## Philosophy

A postmortem that does not change anything is worse than no postmortem. It consumes time and creates the illusion of learning without the reality.

Good postmortems are:
- **Blameless:** Focus on systems, not individuals.
- **Thorough:** Dig to root causes, not just proximate causes.
- **Actionable:** Produce specific, owned follow-ups.
- **Followed through:** Actions are completed, not abandoned.

---

## When to Run a Postmortem

Always run a postmortem for:
- P0 incidents (customer-facing outage, data loss)
- P1 incidents with significant impact
- Near-misses that could have been severe
- Repeat incidents (same failure mode as a previous incident)

Consider running a postmortem for:
- P2 incidents with interesting lessons
- Process failures (missed deadline, major miscommunication)
- Security incidents (regardless of severity)

---

## Timeline

| Milestone | Timing | Owner |
|---|---|---|
| Incident resolved | T+0 | IC |
| Initial timeline documented | T+24 hours | IC or designee |
| Postmortem meeting scheduled | T+48 hours | IC |
| Postmortem meeting held | T+5 business days | Postmortem facilitator |
| Postmortem document finalized | T+7 business days | Postmortem facilitator |
| Action items assigned and tracked | T+7 business days | Engineering manager |

---

## The Postmortem Meeting

### Attendees
- Everyone involved in the incident
- Team lead or manager
- Optional: stakeholders affected by the incident

### Facilitator
Someone not directly involved in the incident. Their job is to keep the discussion productive and blameless.

### Agenda (60 to 90 minutes)

1. **Timeline review (15 min):** Walk through what happened, when. No analysis yet. Just facts.

2. **Impact review (10 min):** What was the customer and business impact? Quantify if possible.

3. **Root cause analysis (30 min):** Why did this happen? Use "5 whys" or similar technique to dig past proximate causes.

4. **Contributing factors (15 min):** What else made this worse? (Detection delay, tooling gaps, communication issues)

5. **Action items (20 min):** What are we going to do to prevent this? Be specific. Assign owners and due dates.

### Rules

**Blameless environment.**
We do not ask "who screwed up?" We ask "what in our system allowed this to happen?"

**Assume good intent.**
Everyone involved was trying to do the right thing. If someone made a mistake, the question is: why was that mistake easy to make?

**Focus on learning, not punishment.**
The goal is to improve. If people fear punishment, they will hide problems.

---

## Root Cause Analysis

### The "5 Whys" Technique

Keep asking "why" until you reach systemic causes.

**Example:**
- Why did the outage happen? The database ran out of connections.
- Why did it run out of connections? A query was holding connections open too long.
- Why was the query holding connections? It was doing a full table scan.
- Why was it doing a full table scan? An index was missing.
- Why was the index missing? The schema migration did not include it.
- Why did the migration not include it? There was no code review checklist for schema changes.

The root cause is not "the query was slow." The root cause is "we have no systematic check for schema changes."

### Common Root Cause Categories

- **Process gap:** No checklist, review, or gate to catch the error.
- **Tooling gap:** No automation, alerting, or safeguard to prevent or detect.
- **Knowledge gap:** The person did not know this could happen.
- **Capacity gap:** The system was not scaled for the load it received.
- **Communication gap:** Information did not reach the right people.

---

## Action Items That Work

Good action items are:
- **Specific:** "Add alerting for connection pool exhaustion" not "improve monitoring."
- **Owned:** One person, not a committee.
- **Time-bound:** Due date, not "when we have time."
- **Verifiable:** You can tell when it is done.

### Prioritizing Action Items

Not all action items are equal. Prioritize by:

1. **Likelihood of recurrence:** How likely is this to happen again?
2. **Severity of impact:** How bad would it be if it recurs?
3. **Effort to implement:** How much work is the fix?

High likelihood + high severity + low effort = do it now.
Low likelihood + low severity + high effort = do not bother.

---

## Follow-Through

The postmortem is not done when the document is written. It is done when the action items are complete.

**Tracking:**
- All action items go into the team's tracking system (Jira, Linear, etc.)
- Review open postmortem actions weekly in team lead sync
- Escalate stalled items

**Closing the Loop:**
- When all action items are complete, mark the postmortem closed
- If an action item is deprioritized, document why

**Measuring Effectiveness:**
- Track repeat incidents. If the same failure mode recurs, the postmortem failed.
- Review postmortem completion rate. If action items are not getting done, fix the process.

---

## Template

See [Postmortem Template](../templates/postmortem-template.md) for the format I use.

---

## Anti-Patterns

**The blame session.**
The meeting becomes about who screwed up. People become defensive. No one learns anything.

**The shallow analysis.**
Stopping at the proximate cause. "The deploy broke prod" is not a root cause.

**The action item graveyard.**
Creating action items that never get done. This is worse than not creating them.

**The copy-paste postmortem.**
Using the same template language without thinking. "Improve monitoring" appears in every postmortem, but nothing changes.

**The forgotten postmortem.**
Running the meeting, writing the document, then never looking at it again.

---

[Back to README](../README.md)
