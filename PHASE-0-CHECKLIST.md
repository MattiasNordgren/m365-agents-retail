<!-- FORK-NEW: This entire file is fork-specific content -->
<!-- Source: IKEA M365 Agents Phase 0 implementation (2026-05-31) -->
<!-- Reapply Priority: HIGH -->

# Phase 0 Foundation Checklist

**Version:** 1.0  
**Date:** 2026-05-31  
**Duration:** 6 weeks  
**Fork Status:** FORK-NEW (not in upstream)

---

## Overview

Phase 0 establishes the foundation for M365 Agents adoption. It answers three questions:

1. **Are we ready?** (Maturity Assessment)
2. **How will we build it?** (Architecture Selection)
3. **How will we run it?** (Governance Design)

**Target Outcome:** Executive approval to proceed to Phase 1 pilot.

---

## Week-by-Week Checklist

### Week 1: Kickoff & Discovery

#### Stakeholder Engagement
- [ ] Identify executive sponsor (CIO/CDO level)
- [ ] Map key stakeholders across IT, business, security, compliance
- [ ] Schedule kickoff meeting with core team
- [ ] Establish communication channels (Teams channel, email list)
- [ ] Define meeting cadences (daily standup, weekly sync)

#### Scope Definition
- [ ] Document business drivers and strategic context
- [ ] Identify target use cases (initial list)
- [ ] Define success criteria for Phase 0
- [ ] Confirm timeline and milestones
- [ ] Identify constraints (budget, timeline, resources)

#### Technical Discovery
- [ ] Document current M365 tenant structure
- [ ] Inventory existing Copilot/AI deployments
- [ ] List available data sources (SharePoint, Dataverse, APIs)
- [ ] Identify integration points (ERP, CRM, custom systems)
- [ ] Review security and compliance requirements

**Week 1 Gate:** Kickoff complete, scope documented, stakeholders identified.

---

### Week 2: Maturity Assessment

#### Strategy Dimension
- [ ] Review existing AI/GenAI strategy documents
- [ ] Interview executive sponsor on vision and investment
- [ ] Assess business case maturity
- [ ] Document roadmap existence and alignment
- [ ] Score and document evidence (L1-L5)

#### Data Dimension
- [ ] Review Microsoft Purview deployment status
- [ ] Assess sensitivity labeling maturity
- [ ] Document data governance policies
- [ ] Review Graph connector configurations
- [ ] Identify RAG readiness
- [ ] Score and document evidence (L1-L5)

#### Tooling Dimension
- [ ] Review Copilot Studio environments
- [ ] Assess CI/CD pipeline maturity
- [ ] Document agent registry status
- [ ] Review DevSecOps practices
- [ ] Score and document evidence (L1-L5)

#### Skills Dimension
- [ ] Inventory AI/ML skills across teams
- [ ] Review training programs
- [ ] Assess Copilot Studio expertise
- [ ] Document prompt/harness engineering maturity
- [ ] Score and document evidence (L1-L5)

#### Governance Dimension
- [ ] Review existing AI governance policies
- [ ] Document compliance framework
- [ ] Assess security review processes
- [ ] Review change management maturity
- [ ] Score and document evidence (L1-L5)

#### Culture Dimension
- [ ] Assess experimentation culture
- [ ] Review adoption patterns of AI tools
- [ ] Document cross-team collaboration
- [ ] Assess change readiness
- [ ] Score and document evidence (L1-L5)

**Week 2 Gate:** Maturity scores documented, gap analysis drafted.

---

### Week 3: Architecture Selection

#### Pattern Evaluation
- [ ] Review three patterns (Tenant-Isolated, Cross-Tenant, Federated Mesh)
- [ ] Score each pattern against criteria
- [ ] Document pros/cons
- [ ] Recommend preferred pattern with rationale

#### Tenant Strategy
- [ ] Document current tenant structure
- [ ] Identify cross-tenant requirements
- [ ] Assess Entra External ID readiness
- [ ] Confirm whether retail tenant is a constrained application tenant or a workforce/collaboration tenant
- [ ] Validate coworker identity baseline (B2B guest default, exception path, POS/local identity if applicable)
- [ ] Validate customer access pattern (approved CIAM path, not tenant user provisioning)
- [ ] Confirm IGA / entitlement orchestration boundaries for groups, roles, SCIM, and D365 connectors
- [ ] Define identity architecture for agents

#### Security Architecture
- [ ] Document zero-trust requirements
- [ ] Define Conditional Access policies
- [ ] Plan secrets management (Key Vault)
- [ ] Document compliance requirements

#### Cost Model (Draft)
- [ ] Estimate platform team FTE costs
- [ ] Estimate Azure consumption
- [ ] Estimate licensing costs
- [ ] Create 3-year TCO projection

**Week 3 Gate:** Architecture pattern selected, draft cost model.

---

### Week 4: Governance Design

#### CoE Model Selection
- [ ] Evaluate models (Dedicated, Federated, Hybrid)
- [ ] Select model based on culture
- [ ] Define core team structure
- [ ] Identify federated network
- [ ] Document CoE charter

#### Team Structure
- [ ] Define Platform Team roles
- [ ] Define AIOps Team roles
- [ ] Map federated contributors
- [ ] Create org chart
- [ ] Identify recruitment needs

#### RACI Matrix
- [ ] Define key workflows
- [ ] Assign R/A/C/I
- [ ] Identify escalation paths
- [ ] Document decision rights

#### Governance Cadences
- [ ] Define operational cadence (weekly)
- [ ] Define tactical cadence (monthly)
- [ ] Define strategic cadence (quarterly)
- [ ] Document communication plan

**Week 4 Gate:** CoE model selected, team structure defined.

---

### Week 5: Business Case & Roadmap

#### Investment Model
- [ ] Finalize cost model
- [ ] Define per-agent cost tracking
- [ ] Identify funding sources
- [ ] Calculate incremental ask
- [ ] Document chargeback model

#### Value Model
- [ ] Define efficiency targets
- [ ] Quantify potential value
- [ ] Estimate payback period
- [ ] Set ROI milestone
- [ ] Document strategic value

#### Phased Roadmap
- [ ] Define Phase 1 scope (pilot)
- [ ] Define Phase 2 scope (scale)
- [ ] Define Phase 3 scope (optimize)
- [ ] Identify go/no-go gates
- [ ] Create timeline visualization

#### Risk Register
- [ ] Identify top 10 risks
- [ ] Assess likelihood and impact
- [ ] Define mitigations
- [ ] Assign risk owners

**Week 5 Gate:** Business case complete, roadmap defined.

---

### Week 6: Executive Approval

#### Stakeholder Reviews
- [ ] Review with technical stakeholders
- [ ] Review with business stakeholders
- [ ] Address feedback
- [ ] Pre-brief executive sponsor

#### Executive Presentation
- [ ] Create executive summary (1-2 pages)
- [ ] Build presentation (15-20 slides)
- [ ] Prepare speaker notes and Q&A
- [ ] Define decisions required

#### Sponsorship Confirmation
- [ ] Document decisions made
- [ ] Obtain budget approval
- [ ] Confirm Platform Team assignment
- [ ] Document Phase 1 kickoff date

**Week 6 Gate:** Executive approval obtained.

---

## Deliverables Summary

| # | Deliverable | Owner | Due |
|---|-------------|-------|-----|
| 1 | Maturity Assessment | Assessment Lead | Week 2 |
| 2 | Gap Analysis | Assessment Lead | Week 2 |
| 3 | Architecture Decision | Architect | Week 3 |
| 4 | Cost Model | Finance Lead | Week 3 |
| 5 | CoE Charter | Governance Lead | Week 4 |
| 6 | RACI Matrix | Governance Lead | Week 4 |
| 7 | Business Case | Program Lead | Week 5 |
| 8 | Roadmap | Program Lead | Week 5 |
| 9 | Risk Register | Program Lead | Week 5 |
| 10 | Executive Summary | Program Lead | Week 6 |
| 11 | Presentation | Program Lead | Week 6 |

---

## Success Criteria

### Phase 0 Complete When:

- ✅ Maturity score documented (all 6 dimensions)
- ✅ Architecture pattern selected
- ✅ CoE model defined
- ✅ Business case approved
- ✅ **Platform Team assigned** (critical)
- ✅ Phase 1 scope confirmed
- ✅ Executive sponsor confirmed

### Red Flags (Escalate):

- 🔴 Platform Team cannot be assigned by Week 3
- 🔴 Executive sponsor not engaged
- 🔴 Budget approval blocked
- 🔴 Security/compliance concerns unresolved

---

## Tips for Success

1. **Start with the answer.** Know your recommendation before presenting options.
2. **Run parallel, not sequential.** Assessment, architecture, governance together.
3. **Platform Team is the blocker.** Escalate early.
4. **Use existing governance.** Integrate, don't create new forums.
5. **API-only pilots first.** Prove value before RAG dependencies.
6. **Document decisions.** You'll need the rationale later.
7. **Weekly executive visibility.** Don't wait 6 weeks.

---

*Adapt timelines based on organizational context.*

<!-- FORK-NEW: End of fork-specific content -->
