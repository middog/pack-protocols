---
title: Territory Watch - Monitoring & Visibility
parent: shepherd
version: 1.0.0
nist_controls:
  - AU-2  # Event Logging
  - AU-6  # Audit Review, Analysis, and Reporting
  - IR-4  # Incident Handling
  - SI-4  # System Monitoring
tags:
  - monitoring
  - siem
  - alerting
  - observability
  - logging
workflow_states:
  - blind
  - logging
  - alerting
  - investigating
  - responding
---

# 👁️ Territory Watch

**Monitoring, Visibility & Alerting**

*~ears rotating like radar dishes, eyes scanning the treeline~* 🐕

The Shepherd watches. Not paranoid, not obsessive—attentive. Knowing what's normal so you can spot what isn't. Territory Watch is how you keep your eyes on the whole pack.

---

## The Core Truth

> **You can't respond to what you don't see.**
> **Alert fatigue is worse than no alerts.**
> **Good monitoring is about signal, not noise.**

The goal isn't to capture everything—it's to see what matters. A Shepherd who barks at every leaf is useless. One who notices the wolf? Invaluable.

---

## The Monitoring Pyramid

```
                     ┌───────────────┐
                     │   RESPONSE    │ ← Incident handling
                     │   (Action)    │
                     └───────┬───────┘
                             │
                     ┌───────▼───────┐
                     │   ANALYSIS    │ ← Investigation, correlation
                     │   (Insight)   │
                     └───────┬───────┘
                             │
                     ┌───────▼───────┐
                     │   ALERTING    │ ← Notifications of anomalies
                     │   (Signal)    │
                     └───────┬───────┘
                             │
                     ┌───────▼───────┐
                     │  AGGREGATION  │ ← SIEM, central logging
                     │   (Context)   │
                     └───────┬───────┘
                             │
                     ┌───────▼───────┐
                     │  COLLECTION   │ ← Logs, metrics, events
                     │   (Data)      │
                     └───────────────┘
```

Start at the bottom and build up. You need solid collection before you can aggregate. You need aggregation before meaningful alerting. Alerting enables analysis. Analysis drives response.

---

## What to Watch

### 🔐 Identity & Access

| Event | Why It Matters | Alert Threshold |
|-------|----------------|-----------------|
| Failed logins | Brute force attempts | >5 in 10 minutes |
| Successful login from new location | Compromised credentials | Any new country/unusual region |
| Privilege escalation | Lateral movement | Any admin elevation |
| Service account usage | Often targeted | Interactive login by service acct |
| MFA bypass or failure | Security control weakened | Any bypass event |
| Password changes | Account takeover | Multiple in short period |

### 🌐 Network Activity

| Event | Why It Matters | Alert Threshold |
|-------|----------------|-----------------|
| Outbound to unusual destination | C2 communication | Known bad IPs, unusual countries |
| Large data transfer | Exfiltration | >500MB to external destination |
| Denied connections | Recon or misconfig | Sustained blocks to sensitive segments |
| DNS anomalies | Tunneling, C2 | Queries to unusual TLDs, high volume |
| Lateral movement | Breach expansion | Internal to internal on admin ports |

### 💻 Endpoint Behavior

| Event | Why It Matters | Alert Threshold |
|-------|----------------|-----------------|
| EDR alerts | Known malicious behavior | Per severity (Critical = immediate) |
| New process execution | Malware, living-off-land | Known-bad hashes, suspicious paths |
| Scheduled task creation | Persistence mechanism | Any new scheduled task |
| Registry modification | Persistence, malware | Sensitive keys (Run, Services) |
| USB insertion | Data theft, malware vector | Policy dependent |

### ☁️ Cloud & SaaS

| Event | Why It Matters | Alert Threshold |
|-------|----------------|-----------------|
| API key usage from new IP | Credential compromise | Any unusual source |
| Resource creation | Resource hijacking | Unexpected instances, storage |
| Permission changes | Privilege escalation | Role assignments, policy changes |
| External sharing | Data leak | Files shared outside org |
| OAuth app consent | Supply chain risk | New app authorizations |

### 📊 Application & Data

| Event | Why It Matters | Alert Threshold |
|-------|----------------|-----------------|
| Database queries | Data access patterns | Unusual volumes, sensitive tables |
| File access | Data surveillance | Mass file access, sensitive folders |
| Email forwarding rules | BEC compromise | External forwards created |
| DLP triggers | Data exfiltration | Any high-severity match |

---

## Alert Severity Framework

Not all alerts are equal. Prioritize:

| Severity | Response Time | Examples |
|----------|---------------|----------|
| **Critical** | Minutes | EDR malware detection, compromised admin account, active data exfiltration |
| **High** | Hours | Failed MFA from privileged account, lateral movement indicators, unusual cloud resource creation |
| **Medium** | Same day | Multiple failed logins, new external sharing, policy violations |
| **Low** | Next business day | Audit findings, compliance drift, informational events |
| **Informational** | As capacity allows | Baseline events, telemetry, trending data |

*~perks ears for critical, flicks ear for informational~* 🐕

---

## Fighting Alert Fatigue

The enemy of good monitoring isn't too few alerts—it's too many. Every ignored alert teaches your pack to ignore alerts.

### Tuning Principles

1. **Start quiet, add incrementally** — Begin with high-confidence alerts, add as you prove value
2. **Every alert should be actionable** — If nobody does anything, why alert?
3. **Review false positives** — A 50% false positive rate means people stop looking
4. **Aggregate related events** — 100 alerts for one incident is noise
5. **Context enrichment** — An IP address means nothing; "IP owned by known threat actor" means everything

### Alert Quality Metrics

| Metric | Target | Indicates |
|--------|--------|-----------|
| **False Positive Rate** | <20% | Alert accuracy |
| **Mean Time to Acknowledge** | <30 min (Critical) | Alert visibility |
| **Alert-to-Incident Ratio** | Varies | Signal vs. noise |
| **Unacknowledged Alerts** | 0 (Critical/High) | Alert fatigue |

---

## The Watchful Rest Position 🐕

A good Shepherd isn't always running. There's an art to attentive rest—watching without exhausting yourself.

### Tiered Monitoring Model

```
┌─────────────────────────────────────────────────────────────┐
│                      TIER 3: ON-CALL                         │
│   Human attention for critical alerts, incident response     │
│   (24/7 for critical systems, business hours otherwise)      │
├─────────────────────────────────────────────────────────────┤
│                      TIER 2: TRIAGE                          │
│   Daily review of medium alerts, weekly trend analysis       │
│   (Security team or MSP during business hours)               │
├─────────────────────────────────────────────────────────────┤
│                      TIER 1: AUTOMATED                       │
│   Automated enrichment, correlation, basic response          │
│   (SIEM rules, SOAR playbooks, 24/7)                        │
├─────────────────────────────────────────────────────────────┤
│                      TIER 0: COLLECTION                      │
│   Always-on logging, metrics gathering, event streaming      │
│   (Agents, cloud APIs, log forwarders)                      │
└─────────────────────────────────────────────────────────────┘
```

### Sustainable On-Call

Don't burn out your Shepherds:
- **Clear escalation paths** — Know who to wake and when
- **Runbooks for common alerts** — Documented response procedures
- **Rotation schedules** — Share the load fairly
- **Recovery time** — Time off after incident response
- **Post-incident review** — Learn, don't blame

---

## Log Management

### What to Log

| Source | Priority | Retention |
|--------|----------|-----------|
| Authentication systems | Critical | 1 year minimum |
| Privileged access | Critical | 1 year minimum |
| Firewall/network | High | 90 days minimum |
| Endpoint (EDR) | High | 90 days minimum |
| Email security | High | 90 days minimum |
| Application access | Medium | 30-90 days |
| System events | Medium | 30 days |
| Debug/verbose | Low | 7 days |

### Log Architecture

```
┌──────────────┐  ┌──────────────┐  ┌──────────────┐
│  Endpoints   │  │   Servers    │  │    Cloud     │
│  (EDR agent) │  │   (Syslog)   │  │    (API)     │
└──────┬───────┘  └──────┬───────┘  └──────┬───────┘
       │                 │                  │
       └─────────────────┼──────────────────┘
                         │
                 ┌───────▼───────┐
                 │ Log Forwarder │
                 │ (Fluentd, etc)│
                 └───────┬───────┘
                         │
                 ┌───────▼───────┐
                 │     SIEM      │
                 │  (Sentinel,   │
                 │   Splunk)     │
                 └───────┬───────┘
                         │
          ┌──────────────┼──────────────┐
          │              │              │
    ┌─────▼────┐  ┌──────▼─────┐  ┌────▼─────┐
    │ Alerting │  │ Dashboards │  │ Archive  │
    │ (PagerD, │  │  (Grafana) │  │  (S3,    │
    │  Teams)  │  │            │  │  Blob)   │
    └──────────┘  └────────────┘  └──────────┘
```

---

## Dashboards & Visualization

### Executive Dashboard (30-second glance)
- Overall security posture (Green/Yellow/Red)
- Open critical incidents
- Compliance status
- Trend indicators

### Operations Dashboard (Daily review)
- Alert volume by category
- Top triggered rules
- Investigation queue
- Patch compliance

### Analyst Dashboard (Working view)
- Detailed alert queues
- Investigation timelines
- Entity lookup
- Rule effectiveness metrics

---

## Investigation Workflow

When an alert triggers:

```
    ┌─────────────┐
    │   ALERT     │
    └──────┬──────┘
           │
    ┌──────▼──────┐
    │   TRIAGE    │ ← Is this real? Context check.
    └──────┬──────┘
           │
    ┌──────▼──────┐
    │   SCOPE     │ ← What's affected? Timeline?
    └──────┬──────┘
           │
    ┌──────▼──────┐
    │  CONTAIN    │ ← Stop the bleeding.
    └──────┬──────┘
           │
    ┌──────▼──────┐
    │ INVESTIGATE │ ← Root cause, full impact.
    └──────┬──────┘
           │
    ┌──────▼──────┐
    │  REMEDIATE  │ ← Fix it permanently.
    └──────┬──────┘
           │
    ┌──────▼──────┐
    │   REVIEW    │ ← What did we learn?
    └─────────────┘
```

---

## Common Tooling

### SIEM/XDR
- **Microsoft Sentinel** — Native to M365, Azure
- **Splunk** — Powerful, flexible, expensive
- **Elastic SIEM** — Open source option
- **CrowdStrike Falcon LogScale** — From EDR vendor
- **Wazuh** — Open source, HIDS + SIEM

### SOAR (Automation)
- **Microsoft Sentinel Playbooks** — Logic Apps based
- **Splunk SOAR (Phantom)** — Enterprise automation
- **Tines** — User-friendly SOAR
- **Shuffle** — Open source SOAR

### Alerting & Incident Management
- **PagerDuty** — On-call management
- **Opsgenie** — Atlassian's answer
- **ServiceNow** — Enterprise ITSM
- **Microsoft Teams** — For smaller operations

---

## Detection Engineering

Good detection rules are:
- **Specific enough** — Low false positives
- **Broad enough** — Catch variants
- **Documented** — Clear what they detect and why
- **Tested** — Validated against known-bad samples
- **Maintained** — Updated as threats evolve

### MITRE ATT&CK Alignment

Map your detection coverage to MITRE ATT&CK framework:

| Tactic | Your Coverage | Priority Gaps |
|--------|---------------|---------------|
| Initial Access | |||||| 60% | Phishing variants |
| Execution | |||||||| 80% | Scripting engines |
| Persistence | |||||| 60% | Registry, scheduled tasks |
| Privilege Escalation | |||| 40% | Service account abuse |
| Defense Evasion | ||| 30% | Living off the land |
| Credential Access | ||||| 50% | Kerberoasting |
| Discovery | || 20% | Often benign-looking |
| Lateral Movement | |||||| 60% | SMB, RDP |
| Collection | || 20% | Quiet exfil |
| Exfiltration | ||||| 50% | Encrypted channels |

---

## Anti-Patterns

### 🚫 The Barking Dog
Alerting on everything. Alert fatigue makes all alerts useless.

### 🚫 The Sleeping Dog
Collecting logs nobody looks at. Visibility without attention is false security.

### 🚫 The Expensive Blind Spot
Spending on tools but not staffing analysis. Tools don't protect; people using tools protect.

### 🚫 The Reactive Watchdog
Only responding to alerts, never hunting. Sophisticated attackers avoid triggers.

### 🚫 The Data Hoarder
Keeping everything forever. Storage costs explode; finding anything becomes impossible.

---

## Hunting vs. Alerting

Alerts catch known-bad patterns. Hunting finds unknown-bad.

| Alerting | Hunting |
|----------|---------|
| Automated | Human-driven |
| Known signatures | Hypotheses |
| Reactive | Proactive |
| High volume | Targeted |
| Always on | Scheduled |

Good Shepherds do both: automated alerting for known threats, regular hunting for what automated tools miss.

*~nose working, following a faint trail~* 🐕

---

## Integration Points

- **[Scent Trails](../scent-trails/)** — Inventory tells you what should be talking
- **[Den Security](../den-security/)** — Hardening generates events to monitor
- **[Pack Compliance](../pack-compliance/)** — Logs prove your controls work

---

*~settles into watchful rest, one eye always half-open~*

**The Territory never sleeps, but the Shepherd knows how to rest without losing awareness.** Alert but not anxious. Watching but not exhausting.

*Stay vigilant.* 👁️🐕
