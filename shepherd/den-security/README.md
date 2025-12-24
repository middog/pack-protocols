---
title: Den Security - Workstation & Server Hardening
parent: shepherd
version: 1.0.0
nist_controls:
  - CM-2  # Baseline Configuration
  - CM-6  # Configuration Settings
  - CM-7  # Least Functionality
  - SC-7  # Boundary Protection
  - SI-2  # Flaw Remediation
tags:
  - hardening
  - configuration
  - baseline
  - endpoints
  - servers
workflow_states:
  - unmanaged
  - baseline-applied
  - hardened
  - monitored
  - compliant
---

# 🏠 Den Security

**Workstation & Server Hardening**

*~inspecting the den entrance, checking the bedding, sniffing for intruders~* 🐕

Every workstation is a den. Every server is a den. The Shepherd ensures each one is properly secured—not a fortress of paranoia, but a healthy home where work can happen safely.

---

## The Core Truth

> **A secure baseline is a gift to your users.**
> **Consistent configuration is how you scale.**
> **Hardening isn't restriction—it's freedom from worry.**

Good den security means your pack can focus on their work instead of worrying about threats. The Shepherd handles the perimeter so others can rest easy.

---

## Hardening Philosophy

### The Golden Rule of Hardening

**Secure by default. Open by exception. Document everything.**

```
    MAXIMUM SECURITY
          ▲
          │   Too tight = nobody can work
          │   
    ──────┼────── SWEET SPOT ← Secure enough, usable enough
          │   
          │   Too loose = incidents waiting to happen
          ▼
    MAXIMUM USABILITY
```

Finding the sweet spot requires knowing your pack:
- What do they actually need to do their jobs?
- What risks are you actually protecting against?
- What compensating controls exist?

*~sniffs thoughtfully~* Don't lock the den so tight the pack can't get in and out.

---

## The Belly-Up Assessment 🐕

Before hardening, understand your exposure. The "belly-up" position is vulnerable—that's why dogs only show it to those they trust. Similarly, a vulnerability assessment requires honesty:

| Assessment Area | Questions to Ask |
|-----------------|------------------|
| **Physical** | Who can touch this device? Where does it live? |
| **Network** | What can reach it? What can it reach? |
| **Identity** | Who can log in? What privileges do they have? |
| **Data** | What sensitive info does it hold or access? |
| **Application** | What software runs here? What's its attack surface? |

Document your belly-up exposure before applying controls.

---

## Configuration Baseline Layers

Think of hardening as layers of protection:

```
┌─────────────────────────────────────────────────────┐
│              APPLICATION HARDENING                   │
│   (App-specific configs, unnecessary features off)   │
├─────────────────────────────────────────────────────┤
│              SOFTWARE CONTROLS                       │
│   (Approved apps only, no shadow installs)          │
├─────────────────────────────────────────────────────┤
│              IDENTITY & ACCESS                       │
│   (MFA, least privilege, local admin removal)       │
├─────────────────────────────────────────────────────┤
│              NETWORK BOUNDARIES                      │
│   (Firewall, segmentation, traffic filtering)       │
├─────────────────────────────────────────────────────┤
│              OS HARDENING                            │
│   (CIS benchmarks, unnecessary services off)        │
├─────────────────────────────────────────────────────┤
│              HARDWARE/FIRMWARE                       │
│   (Secure boot, TPM, BIOS passwords)                │
└─────────────────────────────────────────────────────┘
```

---

## Workstation Hardening Checklist

### 🖥️ Windows Workstations

#### Operating System
- [ ] **Current OS version** — Windows 11 preferred, 10 with current patches minimum
- [ ] **Automatic updates enabled** — Windows Update for Business configured
- [ ] **Disk encryption** — BitLocker enabled, recovery keys escrowed
- [ ] **Secure Boot** — Enabled in BIOS/UEFI
- [ ] **TPM 2.0** — Present and active

#### Identity & Access
- [ ] **Local admin removed** — Standard user accounts for daily work
- [ ] **MFA enforced** — Conditional Access requiring MFA for all logins
- [ ] **Password policy** — Minimum 12 characters, complexity enabled
- [ ] **Screen lock** — Maximum 5 minutes of inactivity
- [ ] **Credential Guard** — Enabled where hardware supports

#### Network
- [ ] **Windows Firewall** — Enabled, default deny inbound
- [ ] **VPN for remote** — Always-on VPN or Conditional Access
- [ ] **Public network restrictions** — Limited capabilities on untrusted networks

#### Endpoint Protection
- [ ] **EDR deployed** — Defender for Endpoint, CrowdStrike, or equivalent
- [ ] **Real-time protection** — Enabled, cloud-delivered
- [ ] **Attack Surface Reduction** — Rules enabled and enforced
- [ ] **Controlled Folder Access** — Protecting critical user folders

#### Application Control
- [ ] **Application allowlisting** — Windows Defender Application Control or AppLocker
- [ ] **Browser hardening** — Edge/Chrome with managed policies
- [ ] **Office hardening** — Macro restrictions, external content blocking
- [ ] **No local admin installs** — Software deployment via Intune/SCCM only

### 🍎 macOS Workstations

#### Operating System
- [ ] **Current macOS** — Latest major version, fully patched
- [ ] **FileVault** — Enabled, recovery key escrowed
- [ ] **SIP enabled** — System Integrity Protection active
- [ ] **Gatekeeper** — Enabled, App Store + identified developers

#### Identity & Access
- [ ] **Standard user** — No admin for daily work
- [ ] **MDM enrolled** — Jamf, Intune, or equivalent
- [ ] **Firmware password** — Set to prevent boot modifications
- [ ] **Screen lock** — Maximum 5 minutes

#### Endpoint Protection
- [ ] **XDR/EDR** — CrowdStrike, Defender, or equivalent
- [ ] **Malware protection** — Real-time scanning enabled
- [ ] **Privacy settings** — Camera, microphone access controlled

---

## Server Hardening Checklist

### 🐧 Linux Servers

#### Operating System
- [ ] **Minimal install** — No GUI, only required packages
- [ ] **Current patches** — Automated patching (unattended-upgrades, dnf-automatic)
- [ ] **SELinux/AppArmor** — Enforcing mode
- [ ] **Secure boot** — If hardware supports

#### Identity & Access
- [ ] **SSH key only** — Password auth disabled
- [ ] **No root SSH** — Root login disabled, sudo required
- [ ] **MFA for admins** — TOTP or hardware key for privileged access
- [ ] **Fail2ban** — Brute force protection active
- [ ] **Sudo logging** — All privileged commands logged

#### Network
- [ ] **iptables/nftables** — Default deny, explicit allows
- [ ] **Unnecessary ports closed** — Only required services listening
- [ ] **TLS everywhere** — All services using encrypted connections
- [ ] **Network segmentation** — In appropriate zone

#### Monitoring
- [ ] **Auditd configured** — Key file and command auditing
- [ ] **Log forwarding** — Centralized logging (syslog-ng, Fluentd)
- [ ] **File integrity monitoring** — AIDE, OSSEC, or equivalent
- [ ] **Process monitoring** — Unusual process detection

### 🪟 Windows Servers

#### Operating System
- [ ] **Server Core** — Where feasible, no GUI
- [ ] **Current patches** — WSUS or Windows Update for Business
- [ ] **Windows Defender** — Enabled unless conflicting EDR
- [ ] **Secure boot & TPM** — Enabled where supported

#### Identity & Access
- [ ] **Local admin renamed** — Default Administrator account renamed/disabled
- [ ] **LAPS deployed** — Unique local admin passwords, rotated
- [ ] **Tier model** — Privileged accounts separate from user accounts
- [ ] **Just-in-Time access** — PAM for admin access where feasible

#### Services & Features
- [ ] **Unnecessary roles removed** — Minimal server features
- [ ] **SMBv1 disabled** — Remove legacy protocol
- [ ] **PowerShell logging** — Script block, module, transcription logging
- [ ] **NTLM restrictions** — Blocked or restricted where possible

---

## The Grooming Session Protocol 🐩

Regular configuration review—like a good brushing that catches tangles before they become mats.

### Weekly Quick Groom
- EDR health check (all agents reporting?)
- Patch compliance snapshot
- Failed login review
- New device enrollment status

### Monthly Deep Groom
- Full baseline compliance scan
- Configuration drift report
- Exception review (are temporary exceptions still needed?)
- Security advisory review

### Quarterly Assessment
- Complete CIS benchmark scan
- Penetration test of sample devices
- Policy effectiveness review
- Tool evaluation

---

## Configuration Management

### Desired State vs. Actual State

```
┌─────────────────┐         ┌─────────────────┐
│  DESIRED STATE  │         │  ACTUAL STATE   │
│  (Your policy)  │◀──────▶│  (What's real)  │
└────────┬────────┘         └────────┬────────┘
         │                           │
         │      ┌─────────────┐      │
         └─────▶│    DELTA    │◀─────┘
                │   (Drift)   │
                └──────┬──────┘
                       │
                       ▼
                ┌─────────────┐
                │  REMEDIATE  │
                │  or ACCEPT  │
                └─────────────┘
```

**Tools for managing desired state:**
- **Windows:** Group Policy, Intune Configuration Profiles, DSC
- **macOS:** MDM profiles (Jamf, Intune), scripts
- **Linux:** Ansible, Chef, Puppet, Salt
- **Cloud:** Terraform, CloudFormation, ARM templates

### Drift Detection

Configuration drift is natural—like a dog's coat growing out. Detect and remediate:

| Drift Type | Example | Response |
|------------|---------|----------|
| **Unauthorized change** | Someone disabled firewall | Alert, investigate, remediate |
| **Natural entropy** | Software update changed defaults | Reapply baseline |
| **Shadow configuration** | Dev installed unauthorized tool | Assess, remove or sanction |
| **Exception creep** | Temporary exception became permanent | Review, close or formalize |

---

## Exception Handling

Sometimes you need to leave a door open. Document it:

### Exception Request Template

| Field | Description |
|-------|-------------|
| `exception_id` | Unique identifier |
| `requestor` | Who's asking |
| `system_affected` | What device/server |
| `control_bypassed` | Which security control |
| `business_justification` | Why is this needed? |
| `risk_assessment` | What's the exposure? |
| `compensating_controls` | What else protects this? |
| `expiration_date` | When does this end? |
| `approver` | Who approved this? |
| `review_date` | When to re-evaluate |

**Exception life cycle:**
1. Request with justification
2. Risk assessment
3. Identify compensating controls
4. Time-bound approval
5. Implementation with monitoring
6. Regular review
7. Closure or renewal

*~cocks head~* No permanent exceptions. Everything gets reviewed.

---

## Common Hardening Frameworks

### CIS Benchmarks
Industry-standard configuration guides for:
- Windows 10/11
- Windows Server
- macOS
- Linux (Ubuntu, RHEL, etc.)
- Cloud platforms

**Levels:**
- Level 1: Basic security, minimal impact
- Level 2: Defense-in-depth, may impact usability

### DISA STIGs
Department of Defense Security Technical Implementation Guides. More stringent than CIS. Required for government contractors.

### Microsoft Security Baselines
Microsoft's recommended configurations. Good starting point for Windows environments. Available via Security Compliance Toolkit.

---

## Rollout Strategy

Don't harden everything at once. Pilot, then expand.

```
    ┌─────────────────┐
    │   PILOT GROUP   │ ← 5-10 devices, IT staff
    └────────┬────────┘
             │ Validate, adjust
             ▼
    ┌─────────────────┐
    │  EARLY ADOPTERS │ ← Power users, friendly depts
    └────────┬────────┘
             │ Gather feedback, tune
             ▼
    ┌─────────────────┐
    │   BROAD DEPLOY  │ ← Everyone else, in waves
    └────────┬────────┘
             │ Monitor, support
             ▼
    ┌─────────────────┐
    │    STEADY STATE │ ← Continuous compliance
    └─────────────────┘
```

---

## Anti-Patterns

### 🚫 The Fortress Fallacy
Locking down so hard nobody can work. Security that people bypass is no security at all.

### 🚫 The Default Den
Never changing from vendor defaults. Defaults are convenient, not secure.

### 🚫 The One-Size-Fits-All
Same configuration for servers handling public websites and those processing PII. Context matters.

### 🚫 The Config-and-Forget
Applying baseline once and never checking again. Drift happens.

### 🚫 The Exception Explosion
So many exceptions that your baseline is meaningless. If everything's an exception, nothing is secured.

---

## Integration Points

- **[Scent Trails](../scent-trails/)** — Inventory tells you what to harden
- **[Territory Watch](../territory-watch/)** — Monitoring validates your hardening
- **[Pack Compliance](../pack-compliance/)** — Hardening proves your controls

---

*~circles three times, settles into the den~*

**A well-secured den is a comfortable den.** Your pack sleeps better knowing the Shepherd has checked the locks.

*Rest easy.* 🏠🐕
