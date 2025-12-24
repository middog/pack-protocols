---
title: Scent Trails - Asset Discovery & Inventory
parent: shepherd
version: 1.0.0
nist_controls:
  - CM-8 # System Component Inventory
  - PM-5 # System Inventory
  - RA-5 # Vulnerability Scanning
tags:
  - asset-management
  - discovery
  - inventory
  - cmdb
workflow_states:
  - unknown
  - discovered
  - classified
  - managed
  - retired
---

# 🐾 Scent Trails

**Asset Discovery & Inventory**

*~nose to the ground, methodically working the grid~* 🐕

You can't protect what you don't know exists. The Shepherd's first job is to sniff out every device, every service, every shadow IT deployment hiding in the tall grass. This is your Scent Trails practice.

---

## The Core Truth

> **Every unknown device is a potential threat vector.**
> **Every unmanaged asset is a compliance gap.**
> **Every shadow IT deployment is someone solving a problem your systems didn't.**

Asset discovery isn't just about security—it's about understanding how your pack actually works versus how the org chart says it should.

---

## Discovery Domains

### 🖥️ Hardware Devices

| Category | What to Find | Common Tools |
|----------|--------------|--------------|
| **Workstations** | Laptops, desktops, VMs | Intune, Tanium, Lansweeper |
| **Servers** | Physical, virtual, cloud instances | SCCM, vCenter, Cloud Consoles |
| **Mobile** | Phones, tablets, field devices | MDM (Intune, Jamf, Workspace ONE) |
| **Network** | Routers, switches, access points | Network scanners, SNMP |
| **IoT/OT** | Printers, sensors, smart devices | Specialized OT tools, Nmap |

### ☁️ Cloud & SaaS

| Category | What to Find | Discovery Method |
|----------|--------------|------------------|
| **IaaS** | VMs, containers, serverless | Cloud provider consoles, Terraform state |
| **PaaS** | Databases, app services | Cloud asset inventory |
| **SaaS** | Sanctioned apps | SSO/IdP logs, CASB |
| **Shadow SaaS** | Unsanctioned apps | CASB, expense reports, browser extensions |

### 👤 Identities

| Category | What to Find | Discovery Method |
|----------|--------------|------------------|
| **Human** | User accounts, service accounts | AD/Entra ID, HRIS integration |
| **Machine** | Service principals, API keys | Secret management tools, code scanning |
| **External** | Vendors, guests, contractors | Access reviews, onboarding records |

### 📊 Data Stores

| Category | What to Find | Discovery Method |
|----------|--------------|------------------|
| **Structured** | Databases, data warehouses | DBA interviews, connection strings |
| **Unstructured** | File shares, SharePoint, cloud storage | DLP tools, storage audits |
| **Shadow** | Personal drives, local files | Endpoint scans, user interviews |

---

## Discovery Workflow

```
    ┌─────────────┐
    │   UNKNOWN   │ ← Things you don't know exist
    └──────┬──────┘
           │ Active/Passive Scanning
           ▼
    ┌─────────────┐
    │  DISCOVERED │ ← Found but not classified
    └──────┬──────┘
           │ Classification & Ownership
           ▼
    ┌─────────────┐
    │  CLASSIFIED │ ← Categorized, owner assigned
    └──────┬──────┘
           │ Policy Application & Management
           ▼
    ┌─────────────┐
    │   MANAGED   │ ← Under active governance
    └──────┬──────┘
           │ End of Life Processing
           ▼
    ┌─────────────┐
    │   RETIRED   │ ← Decommissioned, archived
    └─────────────┘
```

---

## Discovery Methods

### Passive Discovery
*~listening with ears perked, not disturbing the environment~*

- **Network traffic analysis** — Watch flows to identify communicating devices
- **DHCP/DNS logs** — See what's requesting addresses and names
- **Authentication logs** — What's authenticating to your IdP?
- **Firewall logs** — What's trying to talk to the outside world?

**Pros:** Non-disruptive, continuous
**Cons:** Only sees active devices, may miss segmented systems

### Active Discovery
*~actively sniffing, poking noses into corners~*

- **Network scanning** — Nmap, Nessus, Qualys discovery scans
- **Agent-based inventory** — Intune, Tanium, SCCM
- **Cloud API enumeration** — Query provider APIs for resources
- **Credential-based scanning** — WMI, SSH, SNMP queries

**Pros:** More complete, can gather detailed info
**Cons:** Can trigger alerts, may disrupt sensitive systems

### Human Discovery
*~asking the pack where things are buried~* 🦴

- **Interviews** — "What tools does your team actually use?"
- **Expense reports** — What's being paid for outside IT?
- **Browser extensions** — What SaaS shows up in authentication flows?
- **Support tickets** — What are people asking for help with?

**Pros:** Finds shadow IT that scans miss
**Cons:** Time-intensive, depends on honesty

---

## The Sniff Test Protocol 🐽

Quick validation for discovered assets:

| Check | Question | Pass/Fail Criteria |
|-------|----------|-------------------|
| **Ownership** | Does someone own this? | Named owner in system |
| **Purpose** | Why does this exist? | Documented business purpose |
| **Currency** | Is it still needed? | Activity in last 90 days |
| **Compliance** | Does it meet baseline? | Passes security config check |
| **Integration** | Is it in our systems? | Exists in CMDB/inventory |

If an asset fails the Sniff Test, it enters **remediation queue**:
1. Find or assign owner
2. Document purpose
3. Evaluate continued need
4. Bring into compliance
5. Add to managed inventory

---

## Asset Classification

Once discovered, every asset needs classification for appropriate protection:

### By Sensitivity

| Level | Description | Examples |
|-------|-------------|----------|
| **Public** | No harm if exposed | Marketing website, public docs |
| **Internal** | Minor harm if exposed | Org charts, internal wikis |
| **Confidential** | Significant harm if exposed | Financial data, HR records |
| **Restricted** | Severe harm if exposed | PII, trade secrets, CUI |

### By Criticality

| Level | Description | Recovery Time Objective |
|-------|-------------|-------------------------|
| **Non-critical** | Inconvenient if down | Days to weeks |
| **Important** | Productivity impact | Hours to days |
| **Critical** | Business impact | Hours |
| **Mission-critical** | Survival impact | Minutes |

---

## Shadow IT: Reading the Real Scent Trail

Shadow IT isn't necessarily bad—it's signal. *~perks ears with interest~*

When you find unsanctioned tools, ask:

1. **What problem is this solving?** — Someone had a need your systems didn't meet
2. **Who deployed it?** — Not to blame, but to understand
3. **What data is in it?** — Risk assessment
4. **Can we bring it into the fold?** — Sanction, secure, support
5. **Do we need to provide an alternative?** — Meet the underlying need

Shadow IT discovery is **organizational feedback**, not just a security problem.

---

## Inventory System Requirements

Your asset inventory (CMDB) should track:

### Core Fields (Minimum Viable)

| Field | Description |
|-------|-------------|
| `asset_id` | Unique identifier |
| `asset_type` | Category (workstation, server, SaaS, etc.) |
| `name` | Human-readable name |
| `owner` | Accountable person |
| `status` | Active, inactive, retired |
| `discovered_date` | When first found |
| `last_seen` | Most recent activity |

### Extended Fields (Recommended)

| Field | Description |
|-------|-------------|
| `os_version` | Operating system/platform |
| `location` | Physical/logical location |
| `criticality` | Business impact level |
| `sensitivity` | Data classification |
| `compliance_scope` | Which frameworks apply |
| `patch_status` | Current/behind/critical |
| `config_baseline` | Which baseline applies |

---

## Cadence & Rhythms

| Activity | Frequency | Purpose |
|----------|-----------|---------|
| Passive monitoring | Continuous | Catch new/changed devices |
| Active network scan | Weekly | Find devices that don't talk much |
| Cloud asset sync | Daily | Track dynamic cloud resources |
| Full inventory reconciliation | Monthly | Verify completeness |
| Shadow IT review | Quarterly | Assess unsanctioned tools |
| Asset classification audit | Annually | Validate categorizations |

---

## Common Findings

What you'll discover when you really start sniffing:

### 🐾 Ghost Devices
Old hardware nobody remembered. That test server from 2019. The printer that "just works."

*Action: Determine owner, evaluate need, retire or manage.*

### 🐾 Clone Armies
Multiple instances of the same thing deployed independently.

*Action: Consolidate, standardize, reduce attack surface.*

### 🐾 Feral SaaS
Tools that grew organically in departments: that one Trello board, the team's Notion, Marketing's Canva.

*Action: Assess risk, bring under management or provide alternatives.*

### 🐾 Orphan Accounts
Service accounts and API keys outliving their owners or purposes.

*Action: Inventory, assign owners, implement rotation.*

### 🐾 Data Warrens
Pockets of sensitive data in unexpected places—that SharePoint folder, someone's OneDrive.

*Action: DLP scanning, data classification, access review.*

---

## Integration Points

Scent Trails feeds into:

- **[Den Security](../den-security/)** — Can't harden what you haven't found
- **[Territory Watch](../territory-watch/)** — Inventory tells you what should be there
- **[Pack Compliance](../pack-compliance/)** — Asset inventory is audit requirement #1

---

## Anti-Patterns

### 🚫 The One-Time Scan
Running discovery once and calling it done. Assets change constantly.

### 🚫 The Spreadsheet Cemetery
Inventory in Excel that nobody updates. Invest in proper tooling.

### 🚫 The Blame Game
Using shadow IT findings to punish departments. They'll just hide better next time.

### 🚫 The Perfect Inventory
Waiting until you have 100% coverage before taking action. Start with what you find.

---

## Templates

- [Asset Discovery Checklist](templates/discovery-checklist.md)
- [Shadow IT Assessment Template](templates/shadow-it-assessment.md)
- [CMDB Field Specification](templates/cmdb-fields.md)

---

*~lifts head, satisfied~*

**Know your territory.** Every device, every service, every identity. Not because you're paranoid—because you care for the pack.

*The scent doesn't lie.* 🐾
