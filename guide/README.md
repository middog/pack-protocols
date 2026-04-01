---
title: Guide Operations (vCTO)
role: guide
version: 1.0.0
tags:
  - vcto
  - cicd
  - delivery
  - devops
  - automation
---

# Guide Operations

**Release rituals and automations shaped for real flow.**

The Guide leads without dragging. It sees the obstacles before the pack hits them, finds the efficient route, and keeps everyone moving at a sustainable pace. From heroic releases to calm, predictable ship cycles — that's Guide work.

---

## The Guide's Work

```
┌─────────────────────────────────────────────────────────────┐
│                     DELIVERY HEALTH                          │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────────┐   │
│  │ TRAIL BLAZING│  │ PACK COMPUTE │  │    LOB FLOWS     │   │
│  │   (CI/CD)    │  │    (HPC)     │  │  (Integrations)  │   │
│  └──────┬───────┘  └──────┬───────┘  └────────┬─────────┘   │
│         │                 │                    │              │
│         └─────────────────┼────────────────────┘              │
│                           │                                   │
│                   ┌───────▼───────┐                          │
│                   │  FLOW STATE   │                          │
│                   │  (Outcomes)   │                          │
│                   └───────────────┘                          │
└─────────────────────────────────────────────────────────────┘
```

The Guide's three domains:

| Domain | Focus | Key Question |
|--------|-------|--------------|
| [Trail Blazing](trail-blazing/) | CI/CD pipelines, release rituals | *Is code flowing from commit to production?* |
| [Pack Compute](pack-compute/) | HPC, batch processing, resource orchestration | *Can we run the big jobs efficiently?* |
| [LoB Flows](lob-flows/) | Line-of-business automation & integration | *Are the business systems talking to each other?* |

---

## Guide Temperament

The Guide head of your FIDO work has a particular character:

**Confident but not reckless.** The Guide knows the terrain and moves decisively. But it stops when the ground is uncertain, scouts ahead, and adjusts the route rather than charging blindly forward.

**Patient with the pace.** Not every pack moves at the same speed. The Guide matches the cadence to the group's actual capacity, not some theoretical ideal. A sustainable trot beats an exhausting sprint followed by collapse.

**Focused on flow, not features.** The Guide doesn't care about fancy tooling—it cares about whether code ships reliably. A simple, working pipeline beats an impressive, flaky one every time.

---

## The Guide's Rhythms

### Daily Path Checks 🐾
- Pipeline health: any failed builds?
- Deployment status: what shipped today?
- Blockers: what's stuck?
- Quick stand-up pulse

### Weekly Trail Maintenance 🐾🐾
- Build time trends
- Test coverage review
- Deployment frequency check
- Technical debt assessment

### Monthly Route Review 🐾🐾🐾
- Pipeline optimization opportunities
- Infrastructure cost analysis
- Tooling evaluation
- Process retrospective

### Quarterly Trail Blazing 🐾🐾🐾🐾
- Major pipeline improvements
- New automation initiatives
- Architecture evolution
- Capacity planning

---

## Release Cadence Patterns

Every delivery organization has its rhythms — where energy builds toward release. The Guide understands these natural patterns and works with them, not against them.

### Healthy Heat Patterns

**Continuous Flow** — Small, frequent releases. Low drama. The ideal state.
- Commits ship same-day
- Feature flags control exposure
- Rollback is painless
- Heat is evenly distributed

**Sprint-Based** — Regular cadence with predictable releases.
- 2-week sprints common
- Heat builds toward sprint end
- Demo/retro creates release rhythm
- Recovery periods between sprints

**Release Trains** — Larger, scheduled releases.
- Monthly or quarterly
- Multiple teams coordinate
- Heat peaks at release windows
- Longer stabilization needed

### Unhealthy Heat Patterns

**The Heroic Release** 🚫
- All-nighters before launch
- Single person holds all context
- Rollback is terrifying
- Recovery takes days

**The Endless Sprint** 🚫
- No recovery periods
- Constant crunch
- Burnout accumulating
- Quality declining

**The Big Bang** 🚫
- Months between releases
- Massive change sets
- High risk, high stress
- "We'll fix it next release"

---

## DevOps Principles

The Guide embodies DevOps culture:

### 🔄 Flow
Remove bottlenecks. Optimize the whole system, not individual steps. Make work visible.

### ⚡ Feedback
Fail fast, learn fast. Automated testing. Continuous monitoring. Immediate alerts.

### 🧪 Experimentation
Safe-to-fail environments. A/B testing. Feature flags. Blameless postmortems.

### 🤝 Collaboration
Dev + Ops + Security. Shared responsibility. Collective ownership. No silos.

---

## DORA Metrics

The Guide tracks what matters:

| Metric | What It Measures | Elite Performance |
|--------|------------------|-------------------|
| **Deployment Frequency** | How often you ship | Multiple times per day |
| **Lead Time for Changes** | Commit to production | Less than one hour |
| **Change Failure Rate** | % of deployments causing incidents | 0-15% |
| **Time to Restore** | Recovery from failures | Less than one hour |

These metrics correlate with organizational performance. Track them, but don't game them.

---

## Guide vs. Shepherd

The Guide and Shepherd work together but focus on different things:

| Aspect | Shepherd (vCIO) | Guide (vCTO) |
|--------|-----------------|--------------|
| **Focus** | Infrastructure security & stability | Delivery speed & reliability |
| **Question** | "Is it secure?" | "Does it ship?" |
| **Risk lens** | Vulnerability, compliance | Velocity, quality |
| **Tooling** | EDR, SIEM, vulnerability scanners | CI/CD, containers, orchestration |
| **Cadence** | Continuous monitoring | Sprint/release rhythms |

The Guide optimizes the path *through* the infrastructure the Shepherd secures.

---

## Common Tooling

### CI/CD Platforms
- **GitHub Actions** — Native to GitHub, good for most teams
- **GitLab CI** — Integrated if using GitLab
- **Azure DevOps** — Microsoft ecosystem
- **Jenkins** — Self-hosted, highly customizable
- **CircleCI** — Cloud-native, fast builds
- **Argo CD** — GitOps for Kubernetes

### Container Orchestration
- **Kubernetes** — Industry standard, complex
- **Docker Swarm** — Simpler, limited scale
- **Nomad** — HashiCorp's lighter alternative
- **ECS/Fargate** — AWS managed containers

### Infrastructure as Code
- **Terraform** — Multi-cloud, declarative
- **Pulumi** — Programming language IaC
- **CloudFormation** — AWS native
- **ARM/Bicep** — Azure native
- **Ansible** — Configuration + orchestration

### Artifact Management
- **Artifactory** — Universal artifact repo
- **Nexus** — Open source option
- **GitHub Packages** — Native to GitHub
- **AWS ECR / Azure ACR** — Cloud container registries

---

## Getting Started

New to Guide work? Start here:

1. **[Trail Blazing](trail-blazing/)** — Establish your CI/CD foundation
2. **[Pack Compute](pack-compute/)** — Handle compute-intensive workloads
3. **[LoB Flows](lob-flows/)** — Connect your business systems

---

## Anti-Patterns

### 🚫 The Over-Engineered Trail
Building complex pipelines for simple problems. Start simple, add complexity only when needed.

### 🚫 The Flaky Path
Tests that sometimes pass, sometimes fail. Nothing kills confidence like intermittent failures.

### 🚫 The Hero Guide
One person who knows all the pipelines. Bus factor of one. Document and distribute knowledge.

### 🚫 The Tool Collector
Adopting every new DevOps tool. Tool sprawl creates cognitive overhead and security surface.

### 🚫 The Speed Demon
Optimizing for raw speed without considering quality. Fast garbage is still garbage.

---

## Related Domains

- **[Shepherd (vCIO)](../shepherd/)** — The Guide delivers through secured infrastructure
- **[Companion (Transform)](../companion/)** — The Guide builds the pipes; the Companion helps teams use them
- **[Operations](../operations/)** — Guide engagement patterns

---

**The Guide finds the way.** Not the flashiest route, not the most impressive technology — the route that actually gets the pack where it needs to go, reliably, sustainably.
