---
title: Pack Compliance - NIST Frameworks & Security Hygiene
parent: shepherd
version: 1.0.0
nist_alignment:
  - NIST-CSF-2.0
  - NIST-SP-800-171-R3
  - NIST-SP-800-53-R5
tags:
  - compliance
  - nist
  - audit
  - risk-management
  - documentation
workflow_states:
  - unassessed
  - gap-identified
  - remediation-planned
  - control-implemented
  - validated
  - continuous-monitoring
---

# 📋 Pack Compliance

**NIST Frameworks & Security Hygiene**


Compliance isn't about checking boxes—it's about proving the work is done and done well. The Shepherd documents the territory, demonstrates the controls, and shows the receipts when the auditors come sniffing.

---

## The Core Truth

> **Compliance without security is theater.**
> **Security without documentation is invisible.**
> **The best compliance is security you can prove.**

Pack Compliance bridges the gap between "we're secure" and "we can demonstrate we're secure." It's how you translate your Shepherd work into language auditors, regulators, and customers understand.

---

## Why NIST?

NIST frameworks provide:
- **Common language** — Everyone speaks the same security vocabulary
- **Flexible structure** — Adapt to your organization's risk profile
- **Industry acceptance** — Recognized by regulators, customers, insurers
- **Clear guidance** — Not just "what" but "how"

For small to mid-sized organizations, NIST provides credibility without requiring army-sized compliance teams.

---

## Framework Overview

```
┌─────────────────────────────────────────────────────────────────────┐
│                     NIST CYBERSECURITY FRAMEWORK (CSF)              │
│                  High-level risk management structure                │
└────────────────────────────────┬────────────────────────────────────┘
                                 │
         ┌───────────────────────┼───────────────────────┐
         │                       │                       │
         ▼                       ▼                       ▼
┌─────────────────┐   ┌─────────────────┐   ┌─────────────────────┐
│ NIST SP 800-171 │   │ NIST SP 800-53  │   │ Other Standards     │
│ (CUI Protection)│   │ (Federal Info   │   │ (ISO 27001, SOC 2,  │
│ 110+ controls   │   │  Systems)       │   │  CMMC, etc.)        │
│                 │   │ 1000+ controls  │   │                     │
└─────────────────┘   └─────────────────┘   └─────────────────────┘
```

### When to Use What

| Framework | Use When | Typical Audience |
|-----------|----------|------------------|
| **NIST CSF** | General security program maturity | Executives, boards, insurers |
| **NIST SP 800-171** | Handling CUI/government contracts | DoD contractors, federal partners |
| **NIST SP 800-53** | Federal systems, high-security needs | Government agencies, high-risk |
| **ISO 27001** | International operations, certification needed | Global customers, enterprise sales |
| **SOC 2** | SaaS/service provider attestation | Enterprise customers |
| **CMMC** | DoD supply chain (evolving) | Defense contractors |

---

## NIST Cybersecurity Framework (CSF) 2.0

The CSF organizes security into six core functions:

### 🔎 GOVERN (New in 2.0)


| Category | What It Covers |
|----------|----------------|
| Organizational Context | Understand business context, mission, stakeholders |
| Risk Management Strategy | Priorities, risk tolerance, supply chain risk |
| Roles & Responsibilities | Who owns what security functions |
| Policies & Procedures | Documented security program |
| Oversight | Executive involvement, continuous improvement |
| Cybersecurity Supply Chain | Third-party risk management |

### 🔍 IDENTIFY


| Category | What It Covers | Shepherd Domain |
|----------|----------------|-----------------|
| Asset Management | Inventory of devices, software, data | [Scent Trails](../scent-trails/) |
| Risk Assessment | Threat identification, vulnerability assessment | Pack Compliance |
| Improvement | Lessons learned, security improvements | Pack Compliance |

### 🛡️ PROTECT


| Category | What It Covers | Shepherd Domain |
|----------|----------------|-----------------|
| Identity Management | Authentication, access control, MFA | [Den Security](../den-security/) |
| Awareness & Training | Security training, phishing awareness | Pack Compliance |
| Data Security | Encryption, data classification, DLP | [Den Security](../den-security/) |
| Platform Security | Hardening, configuration management | [Den Security](../den-security/) |
| Technology Infrastructure Resilience | Backups, redundancy, recovery | [Den Security](../den-security/) |

### 🔔 DETECT


| Category | What It Covers | Shepherd Domain |
|----------|----------------|-----------------|
| Continuous Monitoring | Security monitoring, log analysis | [Territory Watch](../territory-watch/) |
| Adverse Event Analysis | Incident detection, correlation | [Territory Watch](../territory-watch/) |

### 🚨 RESPOND


| Category | What It Covers | Shepherd Domain |
|----------|----------------|-----------------|
| Incident Management | Response planning, handling, communication | Pack Compliance |
| Incident Analysis | Investigation, root cause | [Territory Watch](../territory-watch/) |
| Incident Response | Containment, eradication, recovery | Pack Compliance |
| Incident Mitigation | Preventing recurrence | Pack Compliance |

### 🔄 RECOVER


| Category | What It Covers | Shepherd Domain |
|----------|----------------|-----------------|
| Incident Recovery Plan Execution | Restore operations | Pack Compliance |
| Incident Recovery Communication | Stakeholder updates | Pack Compliance |

---

## NIST SP 800-171 Rev 3

For organizations handling Controlled Unclassified Information (CUI). 17 control families, 110+ security requirements.

### Control Family Mapping

| Family | # Controls | Primary Focus | Key Concerns |
|--------|------------|---------------|--------------|
| **AC** - Access Control | 22 | Who can access what | Least privilege, account management, remote access |
| **AT** - Awareness & Training | 3 | Security awareness | Training records, role-based training |
| **AU** - Audit & Accountability | 9 | Logging & monitoring | What to log, retention, review |
| **CA** - Assessment | 4 | Compliance verification | Self-assessments, POA&Ms |
| **CM** - Configuration Management | 9 | Secure configurations | Baselines, change control, least functionality |
| **IA** - Identification & Authentication | 11 | Identity verification | MFA, password policy, device authentication |
| **IR** - Incident Response | 6 | Breach handling | Plans, detection, reporting |
| **MA** - Maintenance | 4 | System upkeep | Controlled maintenance, remote maintenance |
| **MP** - Media Protection | 6 | Removable media | USB policy, sanitization |
| **PE** - Physical Protection | 6 | Physical security | Access control, visitor logs |
| **PL** - Planning | 2 | Security planning | System security plans |
| **PS** - Personnel Security | 5 | People security | Screening, termination |
| **RA** - Risk Assessment | 4 | Risk identification | Vulnerability scanning, risk analysis |
| **SA** - System & Services Acquisition | 6 | Procurement security | Third-party services, dev security |
| **SC** - System & Communications Protection | 13 | Network security | Boundary protection, encryption |
| **SI** - System & Information Integrity | 7 | System health | Patching, malware protection, monitoring |
| **SR** - Supply Chain Risk Management | 3 | Vendor risk | Supply chain security, provenance |

### High-Priority Controls for Small Organizations

If you're starting out, prioritize these:

**Tier 1: Foundation** 🐾
- AC-2: Account Management
- AC-3: Access Enforcement
- AU-2: Event Logging
- CM-2: Baseline Configuration
- IA-2: Identification & Authentication
- SI-2: Flaw Remediation

**Tier 2: Visibility** 🐾🐾
- AU-6: Audit Review
- CM-6: Configuration Settings
- RA-5: Vulnerability Scanning
- SC-7: Boundary Protection
- SI-4: System Monitoring

**Tier 3: Maturity** 🐾🐾🐾
- AC-17: Remote Access
- AT-2: Literacy Training & Awareness
- IR-4: Incident Handling
- PE-3: Physical Access Control
- PS-3: Personnel Screening

---

## The Compliance Lifecycle

```
┌─────────────┐     ┌─────────────┐     ┌─────────────┐
│   ASSESS    │────▶│    PLAN     │────▶│  IMPLEMENT  │
│   (Gap)     │     │   (POA&M)   │     │  (Controls) │
└─────────────┘     └─────────────┘     └──────┬──────┘
       ▲                                       │
       │                                       ▼
       │            ┌─────────────┐     ┌─────────────┐
       └────────────│   MONITOR   │◀────│  VALIDATE   │
                    │ (Continuous)│     │   (Audit)   │
                    └─────────────┘     └─────────────┘
```

### 1. Assess (Gap Analysis)


**Objective:** Understand your current state against target framework.

**Activities:**
- Select applicable framework (800-171, CSF, etc.)
- Document current controls
- Identify gaps
- Assess risk of each gap

**Deliverable:** Gap Assessment Report

### 2. Plan (POA&M)


**Objective:** Prioritize and schedule remediation.

**Plan of Action & Milestones (POA&M):**

| Field | Description |
|-------|-------------|
| Control ID | Which control is deficient |
| Weakness | What's the gap |
| Risk Level | High/Medium/Low impact |
| Remediation | What will we do |
| Resources | Who/what/how much |
| Milestone | When will it be done |
| Status | Not started/In progress/Complete |

**Prioritization factors:**
- Severity of the gap
- Effort to remediate
- Dependencies
- Available resources

### 3. Implement (Controls)


**Objective:** Close the gaps.

**For each control:**
1. Document the implementation approach
2. Deploy technical controls
3. Create/update policies
4. Train affected personnel
5. Document evidence of implementation

### 4. Validate (Audit)


**Objective:** Prove controls are working.

**Evidence types:**
- **Screenshots** — Configuration settings
- **Logs** — Event records showing control operation
- **Policies** — Documented procedures
- **Training records** — Attendance, completion certificates
- **Interviews** — Personnel understanding of procedures
- **Technical scans** — Vulnerability reports, config assessments

### 5. Monitor (Continuous)


**Objective:** Maintain compliance over time.

**Activities:**
- Ongoing control effectiveness monitoring
- Change management for security-relevant changes
- Regular vulnerability scanning
- Periodic access reviews
- Annual reassessment

---

## System Security Plan (SSP)

The SSP is your compliance bible—the comprehensive document describing how your security controls are implemented.

### SSP Structure

| Section | Content |
|---------|---------|
| **1. System Identification** | System name, owner, boundaries |
| **2. System Description** | Purpose, architecture, components |
| **3. System Environment** | Network diagrams, data flows |
| **4. Control Implementation** | How each control is satisfied |
| **5. Roles & Responsibilities** | Who does what |
| **6. Interconnections** | External system connections |
| **7. Policies & Procedures** | Supporting documentation |

### SSP Maintenance

| Activity | Frequency | Trigger |
|----------|-----------|---------|
| Minor updates | As needed | Small config changes |
| Section review | Quarterly | Scheduled |
| Full review | Annually | Scheduled |
| Major revision | As needed | Significant system changes, reorg |

---

## Showing the Work

Compliance is about evidence. Types of evidence Shepherds produce:

### Technical Evidence
- Configuration exports (GPO, Intune profiles)
- Scan results (vulnerability, compliance)
- Log samples (authentication, access)
- Dashboard screenshots (monitoring, status)

### Administrative Evidence
- Policies and procedures
- Training records
- Access approval workflows
- Risk assessment documents

### Physical Evidence (if applicable)
- Access logs (badge readers)
- Visitor registers
- Facility photos
- Equipment inventories

### Interview Records
- Walkthrough notes
- Question/answer documentation
- Process demonstrations

---

## Working with Auditors


### Before the Audit

1. **Gather evidence** — Organize by control family
2. **Pre-assess** — Run your own checks first
3. **Brief stakeholders** — Ensure availability
4. **Prepare workspace** — Conference room, network access

### During the Audit

1. **Be honest** — Don't hide gaps; explain remediation plans
2. **Be specific** — Provide evidence, not stories
3. **Take notes** — Document questions and findings
4. **Escalate appropriately** — Know when to involve leadership

### After the Audit

1. **Review findings** — Understand before responding
2. **Accept valid findings** — Don't argue the obvious
3. **Challenge appropriately** — If evidence was missed, provide it
4. **Update POA&M** — Incorporate new findings
5. **Track to closure** — Ensure findings are resolved

---

## Compliance Automation

Don't do compliance manually. Tools that help:

### Compliance Management Platforms
- **Drata** — Automated evidence collection
- **Vanta** — Continuous compliance monitoring
- **Hyperproof** — Compliance workflow management
- **ZenGRC** — Governance, risk, compliance

### Built-in Cloud Tools
- **Microsoft Compliance Manager** — M365/Azure compliance
- **AWS Audit Manager** — AWS compliance assessments
- **GCP Security Command Center** — GCP security posture

### Assessment & Scanning
- **Tenable** — Vulnerability + compliance scanning
- **Qualys** — Cloud security and compliance
- **Chef InSpec** — Compliance as code

---

## Anti-Patterns

### 🚫 The Paper Tiger
Beautiful documentation, no actual controls. Auditors eventually dig deeper.

### 🚫 The Audit Sprint
Scrambling before audits instead of continuous compliance. Exhausting and error-prone.

### 🚫 The Checkbox Shepherd
Implementing controls to pass audits rather than to reduce risk. Missing the point.

### 🚫 The Over-Scoper
Applying every control to every system. Not everything needs maximum security.

### 🚫 The Under-Documenter
Implementing good controls but not documenting. Can't prove what you can't show.

---

## Common Compliance Scenarios

### Scenario: First-Time 800-171 Assessment


1. **Scope the boundary** — What systems handle CUI?
2. **Quick baseline assessment** — Use NIST self-assessment tool
3. **Prioritize high-risk gaps** — Focus on AC, AU, IA, SI first
4. **Create initial SSP** — Even if incomplete
5. **Build POA&M** — Realistic remediation timeline
6. **Implement quick wins** — MFA, patching, logging
7. **Iterate** — Tackle harder controls over time

### Scenario: Continuous Compliance After Initial Certification

1. **Dashboard monitoring** — Control effectiveness metrics
2. **Change management** — Security review of changes
3. **Regular testing** — Quarterly vulnerability scans
4. **Evidence refresh** — Keep documentation current
5. **Annual reassessment** — Full review cycle

---

## Integration Points

- **[Scent Trails](../scent-trails/)** — Asset inventory is compliance requirement #1
- **[Den Security](../den-security/)** — Configuration baselines satisfy many controls
- **[Territory Watch](../territory-watch/)** — Logging proves controls operate

---

## References & Resources

### Official NIST Publications
- [NIST Cybersecurity Framework 2.0](https://www.nist.gov/cyberframework)
- [NIST SP 800-171 Rev 3](https://csrc.nist.gov/publications/detail/sp/800-171/rev-3/final)
- [NIST SP 800-171 Small Business Primer](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.1318.pdf)
- [NIST SP 800-53 Rev 5](https://csrc.nist.gov/publications/detail/sp/800-53/rev-5/final)

### Free Training
- [NIST CSF Online Course](https://csrc.nist.gov/Projects/cybersecurity-framework/nist-cybersecurity-framework-a-quick-start-guide)
- [CISA Cyber Essentials](https://www.cisa.gov/cyber-essentials)

### Assessment Tools
- [NIST 800-171 DoD Self-Assessment](https://www.sprs.csd.disa.mil/)
- [CIS Controls Self-Assessment](https://www.cisecurity.org/controls/cis-controls-self-assessment-tool-cis-csat)

---


**Compliance isn't bureaucracy—it's accountability.** The Shepherd documents the work so others can trust it, verify it, and build on it.

*Show the work.* 📋🐕
