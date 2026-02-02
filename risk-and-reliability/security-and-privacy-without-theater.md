# Security and Privacy Without Theater

How to build real security into engineering culture without performative compliance.

---

## Philosophy

Security theater is when you do things that look secure but do not actually reduce risk. It is common because real security is hard and visible compliance is easy.

My approach: focus on outcomes, not appearances. Ask "does this actually reduce risk?" not "does this check a box?"

---

## Principles

### Security is Everyone's Job

Security is not something the security team does. It is something every engineer does. Security reviews, threat modeling, and secure coding are part of how we build software.

### Defense in Depth

No single control prevents all attacks. Layer controls so that if one fails, others catch the problem. This means: authentication AND authorization AND encryption AND monitoring AND access controls.

### Least Privilege

People and systems should have the minimum access required to do their job. Review and revoke access regularly. Default to deny.

### Secure by Default

Systems should be secure in their default configuration. Security should not require extra effort or special knowledge.

### Assume Breach

Design systems assuming that some components will be compromised. Limit blast radius. Detect anomalies. Have a response plan.

---

## Practical Implementation

### Code Security

**Secure coding training.**
All engineers complete secure coding training. Not a one-time checkbox. Annual refresher with updated content.

**Code review for security.**
Security-relevant changes get explicit security review. Maintain a checklist of common vulnerabilities (injection, auth bypass, data exposure).

**Static analysis.**
Automated scanning for common vulnerabilities. Block merges that introduce known vulnerability patterns.

**Dependency management.**
Track dependencies. Alert on known vulnerabilities. Have a process to patch quickly.

### Infrastructure Security

**Encryption everywhere.**
Data at rest: encrypted. Data in transit: encrypted. No exceptions.

**Access controls.**
Role-based access control (RBAC) for all systems. Regular access reviews. Remove access when roles change.

**Network segmentation.**
Separate production from non-production. Separate customer data from internal systems. Limit lateral movement.

**Secrets management.**
No secrets in code. Use a secrets manager. Rotate secrets regularly.

### Monitoring and Detection

**Audit logging.**
Log security-relevant events: authentication, authorization decisions, data access. Retain logs for compliance period.

**Alerting.**
Alert on anomalies: unusual access patterns, failed auth attempts, privilege escalation. Tune to reduce noise.

**Incident detection.**
Regular review of alerts. Clear escalation path for suspicious activity.

### Privacy

**Data minimization.**
Collect only what you need. Delete what you do not need.

**Purpose limitation.**
Use data only for the purpose it was collected. Do not repurpose without consent.

**Access controls for personal data.**
Limit who can access customer data. Log all access. Regular review.

**Compliance.**
Know your obligations (GDPR, CCPA, HIPAA, etc.). Build compliance into systems, not as an afterthought.

---

## Threat Modeling

For significant features or systems, we do threat modeling before building.

**Process:**
1. **Diagram the system.** What are the components? How do they communicate?
2. **Identify assets.** What are we protecting? (Customer data, credentials, money)
3. **Identify threats.** Who might attack? What might they want? (STRIDE framework: Spoofing, Tampering, Repudiation, Information disclosure, Denial of service, Elevation of privilege)
4. **Identify mitigations.** How do we prevent or detect each threat?
5. **Document and review.** Write it down. Review with security team.

This is not heavyweight process. A threat model for a feature can be done in an hour. The value is in thinking systematically about risk before building.

---

## Security Incidents

### Response

Security incidents follow the same incident response process as operational incidents, with additions:
- Involve security team immediately
- Preserve evidence before remediating
- Assess data exposure
- Determine notification obligations

### Communication

Security incidents require careful communication:
- Legal review before external communication
- Clear internal communication to affected teams
- Customer notification as required by law and contract

### Post-Incident

- Postmortem (blameless, thorough)
- Root cause analysis
- Remediation action items tracked to completion
- Consider external penetration testing if systemic gaps identified

---

## What I Will Not Do

### Security Theater Examples

**Compliance checkbox exercises.**
Filling out questionnaires without changing behavior. If the audit does not improve security, it is wasted effort.

**Useless password policies.**
Forcing password changes every 30 days. This reduces security because people write passwords down or use simple patterns.

**Security through obscurity.**
Relying on attackers not finding things. They will find things.

**Long approval chains.**
Requiring 5 sign-offs for minor changes. This teaches people to work around the process.

### What I Will Do Instead

**Focus on outcomes.**
Measure actual security (vulnerability count, time to patch, incident rate), not compliance checkboxes.

**Make security easy.**
If the secure path is harder than the insecure path, people will take the insecure path. Make secure the default.

**Invest in detection.**
Prevention is important, but assume some attacks will succeed. Invest in detecting and responding quickly.

**Train continuously.**
One training session is not enough. Security awareness is ongoing.

---

## Metrics

| Metric | Target | Why It Matters |
|---|---|---|
| Time to patch critical vulnerabilities | Under X days | Speed of response to known risks |
| Percentage of code covered by static analysis | Y% | Automated vulnerability detection |
| Access review completion rate | Z% quarterly | Ensures least privilege is maintained |
| Security training completion | 100% annually | Baseline security awareness |
| Mean time to detect security incidents | Under X hours | Limits damage from breaches |

---

[Back to README](../README.md)
