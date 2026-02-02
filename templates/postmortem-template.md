# Postmortem Template

A template for documenting and learning from incidents.

---

## How to Use This Template

1. Start filling this out within 24 hours of incident resolution
2. Hold the postmortem meeting within 5 business days
3. Complete the document within 7 business days
4. Track action items to completion

---

## Incident Summary

**Incident title:** [Brief descriptive title]
**Severity:** P0 / P1 / P2 / P3
**Date:** [Date of incident]
**Duration:** [Total time from detection to resolution]
**Incident Commander:** [Name]
**Postmortem Author:** [Name]
**Postmortem Date:** [Date of postmortem meeting]

---

## Executive Summary

[2-3 sentences describing what happened, the impact, and how it was resolved. This should be readable by someone with no technical context.]

---

## Impact

**Customer impact:**
- [Number of customers affected]
- [What they experienced]
- [Duration of impact]

**Business impact:**
- [Revenue impact, if any]
- [SLA implications, if any]
- [Reputational impact, if any]

**Internal impact:**
- [Teams affected]
- [Other work delayed]

---

## Timeline

All times in [timezone].

| Time | Event |
|---|---|
| [HH:MM] | [First anomaly or trigger] |
| [HH:MM] | [Alert fired / customer reported] |
| [HH:MM] | [Incident declared, IC assigned] |
| [HH:MM] | [Key investigation step] |
| [HH:MM] | [Root cause identified] |
| [HH:MM] | [Mitigation implemented] |
| [HH:MM] | [Service restored] |
| [HH:MM] | [Incident closed] |

---

## Root Cause Analysis

### What happened

[Detailed technical description of what failed and why. Include relevant system details.]

### Contributing factors

[What else made this incident worse or more likely? This might include process gaps, communication issues, or technical debt.]

### 5 Whys

1. Why did [the immediate problem] happen?
   - Because [answer]
2. Why did [answer from above] happen?
   - Because [answer]
3. Why did [answer from above] happen?
   - Because [answer]
4. Why did [answer from above] happen?
   - Because [answer]
5. Why did [answer from above] happen?
   - Because [answer]

**Root cause:** [Summary of the underlying systemic issue]

---

## What Went Well

- [Thing that worked well during incident response]
- [Thing that worked well during incident response]
- [Detection, communication, or recovery that was effective]

---

## What Could Be Improved

- [Process or system that did not work well]
- [Gap in detection, response, or recovery]
- [Communication or coordination issue]

---

## Action Items

| Action | Owner | Priority | Due Date | Status |
|---|---|---|---|---|
| [Specific action to prevent recurrence] | [Name] | P0 / P1 / P2 | [Date] | Open / In Progress / Done |
| [Specific action to improve detection] | [Name] | P0 / P1 / P2 | [Date] | Open / In Progress / Done |
| [Specific action to improve response] | [Name] | P0 / P1 / P2 | [Date] | Open / In Progress / Done |

**Prioritization guidance:**
- P0: Must do immediately. Prevents recurrence of same incident.
- P1: Do this quarter. Improves detection or response.
- P2: Nice to have. General improvement.

---

## Lessons Learned

[What did we learn from this incident that applies beyond the specific technical fix? This might be about process, architecture, or team practices.]

---

## Appendix

### Relevant Links

- [Link to incident channel]
- [Link to dashboards]
- [Link to logs]
- [Link to related documents]

### Participants

**Incident response:**
- [Name, role]
- [Name, role]

**Postmortem meeting:**
- [Name, role]
- [Name, role]

---

## Postmortem Quality Checklist

Before marking this postmortem complete, verify:

- [ ] Timeline is complete and accurate
- [ ] Root cause is identified (not just proximate cause)
- [ ] Impact is quantified
- [ ] Action items are specific and owned
- [ ] Action items have due dates
- [ ] Lessons learned are documented
- [ ] Postmortem is shared with relevant stakeholders

---

[Back to README](../README.md)
