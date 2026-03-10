# Raspberry Pi 4 Security Monitoring Lab

> Home security lab built to develop hands-on SOC skills: log analysis, alert triage, and incident investigation on a self-hosted Linux environment.

---

## Overview

Built and documented a Raspberry Pi based security monitoring lab to develop hands-on experience with system monitoring, authentication events, and alert investigation. Configured Linux logging and centralized monitoring to identify failed login attempts and suspicious access activity.

**Focus areas:** Alert triage · SSH brute-force detection · Authentication event analysis · Incident documentation

---

## Architecture

```
[Network Traffic]
       │
       ▼
  [Raspberry Pi 4]
  ┌─────────────────────────────┐
  │  Suricata (Network IDS)     │  ← Detects suspicious traffic
  │  Pi-hole (DNS monitoring)   │  ← Flags suspicious domains
  │  Wazuh Agent (SIEM)         │  ← Centralizes logs & alerts
  │  Linux Auth Logs            │  ← Tracks login attempts
  └─────────────────────────────┘
       │
       ▼
  [Wazuh Dashboard]
  Alert triage · Incident review · Response documentation
```

---

## Tools & Stack

| Tool | Purpose |
|------|---------|
| **Raspberry Pi OS Lite** | Base Linux environment |
| **Wazuh** | SIEM — log aggregation, alert triage, rule-based detection |
| **Suricata** | Network IDS — traffic analysis, threat signatures |
| **Pi-hole** | DNS-layer monitoring — suspicious domain detection |
| **Linux Auth Logs** | Authentication event tracking (failed logins, SSH attempts) |

---

## Incidents Investigated

### SSH Brute-Force Simulation
- **Detection:** Wazuh triggered alerts on repeated failed SSH authentication attempts
- **Triage:** Reviewed source IP, timing patterns, and frequency of attempts
- **Response:** Documented findings, identified attack pattern, noted remediation steps (fail2ban, key-only auth)
- **Outcome:** Practiced full triage-to-documentation workflow

### Suspicious DNS Query Detection
- **Detection:** Pi-hole flagged outbound queries to known suspicious domains
- **Triage:** Reviewed query logs, identified source device on network
- **Outcome:** Practiced DNS-based threat investigation

---

## Key Takeaways

- Hands-on experience with SIEM alert triage workflow
- Practiced translating raw log data into structured incident documentation
- Developed familiarity with Linux authentication logs and common attack patterns
- Built understanding of layered detection (network + DNS + host)

---

## Background

This lab supports my transition from IT Support Specialist (U.S. Department of Labor, BLS) to SOC Analyst. My federal IT background includes 3 years of user access management, MFA troubleshooting, and endpoint support in a compliance-driven environment.

**Certifications:** CompTIA Security+ · Microsoft SC-900

---

## Next Steps

- [ ] Add KQL queries for Microsoft Sentinel practice
- [ ] Document additional attack simulations
- [ ] Integrate Kibana for log visualization
