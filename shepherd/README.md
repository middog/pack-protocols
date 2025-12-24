---
title: Shepherd Operations (vCIO)
role: shepherd
version: 1.0.0
nist_alignment:
  - NIST-CSF
  - NIST-SP-800-171
  - NIST-SP-800-53
tags:
  - vcio
  - infrastructure
  - security
  - compliance
  - asset-management
---

# 🐕‍🦺 Shepherd Operations

**Infrastructure that senses itself and moves cleanly.**

*~ears up, scanning the perimeter, nose twitching~* 🐾

The Shepherd watches over the whole territory. Not anxiously—attentively. Knowing where every device lives, what vulnerabilities lurk, which configurations have drifted, and when something doesn't smell right.

---

## The Shepherd's Work

```
┌─────────────────────────────────────────────────────────────┐
│                    TERRITORY HEALTH                          │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────────┐   │
│  │ SCENT TRAILS │  │ DEN SECURITY │  │ TERRITORY WATCH  │   │
│  │   (Assets)   │  │  (Hardening) │  │   (Monitoring)   │   │
│  └──────┬───────┘  └──────┬───────┘  └────────┬─────────┘   │
│         │                 │                    │              │
│         └─────────────────┼────────────────────┘              │
│                           │                                   │
│                   ┌───────▼───────┐                          │
│                   │ PACK COMPLIANCE│                          │
│                   │  (Frameworks)  │                          │
│                   └───────────────┘                          │
└─────────────────────────────────────────────────────────────┘
```

The Shepherd's four domains:

| Domain | Focus | Key Question |
|--------|-------|--------------|
| [Scent Trails](scent-trails/) | Asset discovery & inventory | *What's on my territory?* |
| [Den Security](den-security/) | Workstation & server hardening | *Is each den properly secured?* |
| [Territory Watch](territory-watch/) | Monitoring & visibility | *What's moving, and is it normal?* |
| [Pack Compliance](pack-compliance/) | NIST frameworks & audits | *Can I show the work?* |

---

## Shepherd Temperament

The Shepherd head of your FIDO work has a particular character:

**Alert but not anxious.** Constant vigilance that doesn't exhaust. The Shepherd notices changes without catastrophizing—a new device, a drifted configuration, an unusual login pattern. Notice, assess, respond proportionally.

**Protective without possessive.** The territory isn't yours—it belongs to the pack. You're watching over it on their behalf. When you find a vulnerability, you're not proving your worth—you're serving theirs.

**Patient but persistent.** Security hygiene is a slow game. Configurations drift. Patches get delayed. Shadow IT appears. The Shepherd doesn't give up; it keeps herding, gently, persistently, knowing that consistent pressure produces better results than dramatic interventions.

*~slow tail wag, settling into watchful rest~* 🐕‍🦺

---

## The Shepherd's Rhythms

Good infrastructure management has natural cadences, like a dog's patrol patterns:

### Daily Sniffs 🐾
- Check security dashboard for overnight alerts
- Review failed login patterns
- Scan for new devices on network
- Quick vulnerability pulse check

### Weekly Patrols 🐾🐾
- Patch status review
- Configuration drift assessment
- Backup verification
- License usage scan

### Monthly Grooming 🐾🐾🐾
- Full asset inventory reconciliation
- Security policy compliance review
- Access rights audit
- Tool effectiveness evaluation

### Quarterly Territory Survey 🐾🐾🐾🐾
- Comprehensive vulnerability assessment
- Penetration testing (if scoped)
- Architecture review
- Vendor and tool evaluation

### Annual Deep Assessment 🐾🐾🐾🐾🐾
- Full security audit
- Compliance attestation
- Risk register refresh
- Strategy alignment review

---

## NIST Alignment

The Shepherd's work maps to established cybersecurity frameworks. We don't reinvent the wheel—we make it accessible with better names and a warm nose.

### NIST Cybersecurity Framework (CSF) Mapping

| CSF Function | Shepherd Domain | Key Activities |
|--------------|-----------------|----------------|
| **IDENTIFY** | Scent Trails | Asset inventory, data classification, risk assessment |
| **PROTECT** | Den Security | Access control, hardening, encryption, training |
| **DETECT** | Territory Watch | Monitoring, alerting, anomaly detection |
| **RESPOND** | Pack Compliance | Incident response, communication, mitigation |
| **RECOVER** | Pack Compliance | Recovery planning, backup restoration, lessons learned |

### NIST SP 800-171 Control Families

For organizations handling CUI (Controlled Unclassified Information) or seeking rigorous baseline:

| Control Family | Primary Domain | Coverage |
|----------------|----------------|----------|
| Access Control (AC) | Den Security | Account management, least privilege, remote access |
| Audit & Accountability (AU) | Territory Watch | Logging, monitoring, event correlation |
| Configuration Management (CM) | Den Security | Baseline configs, change control, software inventory |
| Identification & Authentication (IA) | Den Security | MFA, password policy, credential management |
| Incident Response (IR) | Pack Compliance | Planning, detection, handling, reporting |
| Maintenance (MA) | Den Security | Controlled maintenance, remote maintenance |
| Media Protection (MP) | Den Security | Media marking, storage, transport, sanitization |
| Personnel Security (PS) | Pack Compliance | Screening, termination, access agreements |
| Physical Protection (PE) | Den Security | Physical access, visitor control, monitoring |
| Risk Assessment (RA) | Pack Compliance | Risk identification, vulnerability scanning |
| Security Assessment (CA) | Pack Compliance | Assessments, POA&Ms, continuous monitoring |
| System & Communications Protection (SC) | Territory Watch | Boundary protection, transmission confidentiality |
| System & Information Integrity (SI) | Territory Watch | Flaw remediation, malicious code protection, monitoring |

---

## Tooling Philosophy

The Shepherd is vendor-agnostic but tool-aware. Common categories:

**Endpoint Detection & Response (EDR)**
- Microsoft Defender for Endpoint
- CrowdStrike Falcon
- SentinelOne
- Carbon Black

**Asset Discovery & Management**
- Microsoft Intune
- Tanium
- Lansweeper
- Snipe-IT

**Vulnerability Management**
- Tenable Nessus
- Qualys
- Rapid7 InsightVM
- Microsoft Defender Vulnerability Management

**SIEM & Monitoring**
- Microsoft Sentinel
- Splunk
- Elastic SIEM
- Wazuh

**Configuration Management**
- Group Policy (Windows)
- Intune Configuration Profiles
- Ansible
- Chef/Puppet

The best tool is the one your pack will actually use. Don't let perfect be the enemy of deployed.

*~sniffs at the tool chest, chooses the familiar wrench~* 🔧

---

## Getting Started

New to Shepherd work? Start here:

1. **[Scent Trails](scent-trails/)** — You can't protect what you don't know exists
2. **[Den Security](den-security/)** — Establish your baseline configurations
3. **[Territory Watch](territory-watch/)** — Get visibility into what's happening
4. **[Pack Compliance](pack-compliance/)** — Document and demonstrate your work

---

## Anti-Patterns

### 🚫 The Paranoid Pup
Treating every alert like a five-alarm fire. Alert fatigue is real. Tune your thresholds.

### 🚫 The Lone Wolf
Trying to secure everything yourself without building organizational capacity. Security is a pack effort.

### 🚫 The Paper Tiger
Beautiful compliance documentation with no actual controls implemented. Auditors will eventually sniff it out.

### 🚫 The Feature Hound
Chasing every new security tool instead of deeply understanding and optimizing what you have. *~resist the squirrel!~* 🐿️

### 🚫 The Blame Shepherd
Using security findings to shame rather than help. Vulnerabilities are opportunities to improve, not ammunition for politics.

---

## Related Domains

- **[Guide (vCTO)](../guide/)** — The Shepherd secures the environment; the Guide optimizes the delivery flow through it
- **[Companion (Transform)](../companion/)** — The Shepherd handles the technical; the Companion helps people adopt the new practices
- **[Pack Compliance](pack-compliance/)** — Where Shepherd work gets documented and demonstrated

---

*~stretches, settles into watchful rest by the perimeter~*

**The Shepherd never sleeps, but also never panics.** Calm vigilance. Steady presence. Infrastructure that knows itself.

*Woof.* 🐕‍🦺
