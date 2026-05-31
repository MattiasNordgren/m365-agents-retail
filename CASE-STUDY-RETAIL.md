<!-- FORK-NEW: This entire file is fork-specific content -->
<!-- Source: IKEA M365 Agents Phase 0 implementation (2026-05-31) -->
<!-- Reapply Priority: HIGH -->

# Case Study: M365 Agents Implementation in Global Retail

**Version:** 1.0  
**Date:** 2026-05-31  
**Type:** Anonymized implementation case study  
**Fork Status:** FORK-NEW (not in upstream)

---

## Executive Summary

A global retail organization with **28 markets**, **dual Entra ID tenants** (Corporate + Retail), and a **Fall 2026 agentic commerce deadline** successfully completed Phase 0 foundation work in 6 weeks. This case study documents their journey, decisions, and learnings to help other organizations accelerate their M365 agents adoption.

### Key Outcomes

| Metric | Result |
|--------|--------|
| **Maturity Score** | 3.7/5.0 (ready to proceed) |
| **Architecture Pattern** | Pattern B (Dual-Tenant Agents) |
| **Investment** | €2.33M over 3 years (€888K Year 1) |
| **Team Model** | Hybrid CoE: 6 FTE core + 12+ federated |
| **Timeline** | Phase 1 pilot (3 months) → Phase 2 scale (6 months) → Fall 2026 live |

---

## Organization Context

### Business Profile

- **Industry:** Franchise retail
- **Scale:** 28 markets, thousands of stores, millions of customers
- **Workforce:** Mix of corporate knowledge workers and frontline retail associates
- **Digital maturity:** Strong cloud foundation (Microsoft stack), ERP modernization in progress

### IT Landscape

| Domain | Current State |
|--------|---------------|
| **Identity** | Dual tenant: Corporate (knowledge workers) + Retail (store operations, customer-facing) |
| **M365 Licenses** | Primarily E5, Copilot licenses in place |
| **Cloud Platform** | Azure with mature DevOps (GitHub Actions + ADO) |
| **Data Platform** | CRM and ERP connected, data catalog in progress |
| **Observability** | Splunk + Application Insights, MELT pillars |

### Strategic Drivers

1. **Agentic commerce deadline:** Business commitment to launch customer-facing agents by Fall 2026
2. **Efficiency mandate:** 20%+ productivity gains target across 28 markets
3. **Platform vision:** Create reusable capability, not one-off pilots
4. **Maturity model:** Serve as template for other business units

---

## Phase 0: Foundation (6 Weeks)

### Week 1-2: Maturity Assessment

**Approach:** Interview-based assessment using the 6-dimension maturity framework.

**Results:**

| Dimension | Score | Evidence |
|-----------|-------|----------|
| **Strategy** | 4.0 | Clear vision, executive sponsorship, business case defined |
| **Skills** | 4.0 | 45+ engineers trained, GenAI workshops 80% complete |
| **Governance** | 4.0 | Mature DevOps, ISAE 3402 compliant, clear decision frameworks |
| **Tooling** | 3.5 | Copilot Studio tested in both tenants, Purview pending |
| **Culture** | 3.5 | Experimentation encouraged, cross-team collaboration growing |
| **Data** | 3.0 | CRM/ERP connected, RAG infrastructure and data catalog pending |
| **Overall** | **3.7** | Ready to proceed with targeted gap closure |

**Key Finding:** Organization stronger in "soft" dimensions (Strategy, Skills, Governance, Culture) than "hard" infrastructure (Data, Tooling). This enabled a "start now, build in parallel" approach.

### Week 3-4: Architecture Selection

**Pattern Evaluation:**

| Pattern | Description | Score | Decision |
|---------|-------------|-------|----------|
| **A: Corporate-Only** | All agents in corporate tenant | 6/10 | ❌ Doesn't support customer-facing use cases |
| **B: Dual-Tenant** | Agents in both tenants with cross-tenant identity | 8/10 | ✅ **SELECTED** - fastest path to agentic commerce |
| **C: Federated Mesh** | Centralized governance, distributed execution | 7/10 | ❌ More complexity than needed for initial phases |

**Pattern B Selection Rationale:**

1. **Existing structure:** Organization already operates dual tenants; no consolidation needed
2. **Time to value:** Cross-tenant identity (Entra External ID) faster than tenant migration
3. **Risk isolation:** Corporate and retail data remain separated
4. **Future flexibility:** Can evolve to native multi-tenant mode as Microsoft roadmap matures

**Cost Model:**

| Category | Annual Cost |
|----------|-------------|
| Platform Team (4 FTEs) | €480K |
| AIOps Team (2 FTEs) | €240K |
| Azure consumption | Included in existing commitment |
| Licensing (Agent 365, Purview) | Variable by usage |
| **Total Operating** | **€720K/year** |
| **One-time Setup** | **€168K** |

### Week 4-5: Governance Design

**Model Selected:** Hybrid CoE (small dedicated core + federated network)

**Structure:**

```
                    ┌─────────────────────────┐
                    │    CORE TEAM (6 FTE)    │
                    │                         │
                    │  Platform Team: 4 FTEs  │
                    │  AIOps Team: 2 FTEs     │
                    └───────────┬─────────────┘
                                │
    ┌───────────────────────────┼───────────────────────────┐
    │                           │                           │
    ▼                           ▼                           ▼
┌─────────┐              ┌─────────────┐             ┌──────────┐
│  Dev    │              │ GenAI       │             │ Security │
│ (2 FTE) │              │ Adoption    │             │ (2 FTE)  │
│         │              │ (3 FTE)     │             │          │
└─────────┘              └─────────────┘             └──────────┘
                                │
                    ┌───────────▼───────────┐
                    │ Platform Teams (40+)  │
                    │  Federated support    │
                    └───────────────────────┘
```

### Week 5-6: Business Case & Roadmap

**4-Phase Roadmap:**

```
PHASE 0         PHASE 1          PHASE 2           PHASE 3
Foundation      Pilot            Scale             Optimize
───────────────────────────────────────────────────────────────►

Weeks 1-6       Months 1-3       Months 4-9        Months 10-12+
✅ Complete     2-3 agents       10-20 agents      28 markets
                2-3 markets      5-10 markets      Full portfolio
                API-only         Agentic commerce  Positive ROI
                                 ↑
                            Fall 2026
```

**Business Case Summary:**

| Metric | Target |
|--------|--------|
| Year 1 Investment | €888K (€720K operating + €168K setup) |
| Year 2-3 Investment | €720K/year |
| 3-Year Total | €2.33M |
| Efficiency Target | 20%+ across 28 markets |
| Potential Annual Value | €11.5M (if target achieved) |
| Payback Period | 6-12 months |
| ROI Positive | Month 12 |

---

## Critical Success Factors

### What Worked Well

1. **Start with the answer:** Used Pyramid Principle in all executive communications
2. **Parallel workstreams:** Ran assessment, architecture, and governance in parallel
3. **Build vs Buy clarity:** Used Microsoft-native stack (Copilot Studio, Agent 365, Purview)
4. **Principle-based governance:** Established guardrails so teams could decide without escalation
5. **API-only pilots first:** Started with simple agents to prove value before RAG dependencies

### Critical Blockers Identified

| Blocker | Impact | Mitigation |
|---------|--------|------------|
| **Platform Team not assigned** | Cannot start Phase 1 | Escalate to executive sponsor; Week 3 hard deadline |
| **Purview not deployed** | Compliance baseline missing | Include in Phase 1 Month 1 |
| **RAG infrastructure pending** | Limits knowledge-based agents | Run parallel data track |
| **AIOps roles not hired** | Cannot scale operations | Start hiring in Phase 1 Month 2 |

### Anti-Patterns Avoided

1. **"Build infrastructure first"** — Started with use cases instead
2. **"Heavy central CoE"** — Used lightweight hybrid model
3. **"Pilot in isolation"** — Connected to production from Day 1
4. **"Custom governance platform"** — Used Agent 365 native capabilities
5. **"Generic AI strategy"** — Tied to specific business commitment (Fall 2026)

---

## Lessons Learned

### Organizational

1. **Platform Team is the single biggest dependency.** Assign before Phase 1 starts.
2. **Hybrid CoE matches distributed cultures.** Strong team autonomy resists centralization.
3. **Federated contributors need clear RACI.** Without it, accountability diffuses.
4. **Executive visibility cadence matters.** Weekly operational, monthly steering, quarterly strategic.

### Technical

1. **Dual-tenant is pragmatic, not ideal.** Works when consolidation isn't feasible.
2. **Purview deployment gates compliance.** Include in Month 1.
3. **API-only agents prove value faster.** Save RAG for Phase 2.
4. **6 FTE core team is minimum viable.** 4 platform + 2 operations.

### Financial

1. **Per-agent cost ranges widely (€1,450-3,600/month).** Depends on complexity.
2. **Operating cost dominates TCO.** ~85% operating, ~15% setup over 3 years.
3. **Chargeback enables discipline.** Track and allocate from Day 1.
4. **ROI by Month 12 is realistic.** With 20% efficiency target.

---

## Artifacts Produced

| Deliverable | Purpose | Size |
|-------------|---------|------|
| Executive Summary | Decision document | 2 pages |
| Maturity Assessment | 6-dimension scoring | 15 pages |
| Architecture Decision | Pattern selection | 20 pages |
| Governance Design | CoE structure, RACI | 25 pages |
| Business Case | Investment, ROI | 15 pages |
| Phased Roadmap | Timeline, milestones | 10 pages |
| Stakeholder Map | RACI across workstreams | 5 pages |
| Risk Register | Top risks, mitigations | 5 pages |

---

## Conclusion

**The single most important decision:** Assign the Platform Team before Phase 1 starts.

**Key metrics to track:**
- Phase 1 pilot success (75%+ intent accuracy, 15%+ efficiency)
- Platform Team ramp (4 FTEs operational by Month 1)
- Data foundation progress (Purview Month 1, RAG Month 2-3)
- Fall 2026 agentic commerce readiness

---

*This case study is anonymized. Specific organization details removed for broader applicability.*

<!-- FORK-NEW: End of fork-specific content -->
