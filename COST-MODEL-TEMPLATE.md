<!-- FORK-NEW: This entire file is fork-specific content -->
<!-- Source: IKEA M365 Agents Phase 0 implementation (2026-05-31) -->
<!-- Reapply Priority: MEDIUM -->

# Cost Model Template for M365 Agents

**Version:** 1.0  
**Date:** 2026-05-31  
**Fork Status:** FORK-NEW (not in upstream)

---

## Overview

This template provides a framework for estimating M365 agent implementation costs. Based on real-world implementation data from a global retail organization.

---

## Quick Reference: Per-Agent Costs

| Agent Complexity | Monthly Cost | Characteristics |
|------------------|--------------|-----------------|
| **Simple** | €1,450/month | API-only, single data source, <1K queries/day |
| **Standard** | €2,500/month | RAG-enabled, 2-3 data sources, 1-10K queries/day |
| **Complex** | €3,600/month | Multi-agent, enterprise integrations, >10K queries/day |

---

## Team Cost Model

### Core Team (Minimum Viable)

| Role | FTE | Monthly Cost | Annual Cost |
|------|-----|--------------|-------------|
| Platform Team Leader | 1.0 | €12,000 | €144,000 |
| Copilot Studio Engineer | 1.0 | €10,000 | €120,000 |
| IAM/Security Engineer | 1.0 | €11,000 | €132,000 |
| Data/RAG Engineer | 1.0 | €10,000 | €120,000 |
| **Platform Subtotal** | **4.0** | **€43,000** | **€516,000** |

| Role | FTE | Monthly Cost | Annual Cost |
|------|-----|--------------|-------------|
| AIOps Engineer 1 | 1.0 | €9,000 | €108,000 |
| AIOps Engineer 2 | 1.0 | €9,000 | €108,000 |
| **AIOps Subtotal** | **2.0** | **€18,000** | **€216,000** |

| **Total Core Team** | **6.0** | **€61,000** | **€732,000** |

*Note: Costs include salary, benefits, and overhead. Adjust for local market rates.*

### Federated Contributors (Not Incremental)

| Team | Contributors | Role | Cost Impact |
|------|--------------|------|-------------|
| Development | 2 FTE | Agent development | Existing budget |
| GenAI Adoption | 3 FTE | Training, adoption | Existing budget |
| Security | 2 FTE | Reviews, compliance | Existing budget |
| Platform Teams | 40+ FTE | Domain expertise | Existing budget |

---

## Infrastructure Costs

### Azure Consumption

| Component | Monthly Estimate | Notes |
|-----------|------------------|-------|
| Azure AI Search | €500-2,000 | Depends on index size |
| Azure OpenAI | €1,000-5,000 | Token consumption |
| Azure Functions | €200-500 | API orchestration |
| Azure Key Vault | €50-100 | Secrets management |
| Application Insights | €200-500 | Observability |
| **Subtotal** | **€2,000-8,000** | Per environment |

### Licensing

| License | Per User/Month | Coverage |
|---------|----------------|----------|
| M365 E5 | ~€55 | Base productivity |
| Copilot for M365 | €30 | Copilot access |
| Agent 365 | €15 | Agent governance (or included in E7) |
| Microsoft Purview | Variable | Data governance |

---

## One-Time Setup Costs

| Activity | Estimate | Duration |
|----------|----------|----------|
| Environment provisioning | €30,000 | 2 weeks |
| Purview deployment | €25,000 | 3 weeks |
| CI/CD pipeline setup | €20,000 | 2 weeks |
| Initial agent development | €40,000 | 4 weeks |
| Security baseline | €25,000 | 2 weeks |
| Training & enablement | €15,000 | Ongoing |
| **Total Setup** | **€155,000-180,000** | 8-12 weeks |

---

## 3-Year Total Cost of Ownership

### Scenario: Medium Enterprise (6 FTE core, 10 agents, 5 markets)

| Year | Operating | Setup | Total |
|------|-----------|-------|-------|
| Year 1 | €720,000 | €168,000 | €888,000 |
| Year 2 | €720,000 | — | €720,000 |
| Year 3 | €720,000 | — | €720,000 |
| **3-Year Total** | **€2,160,000** | **€168,000** | **€2,328,000** |

### Cost Composition

```
        Operating Costs (93%)
        ┌────────────────────────────────────────────────────┐
        │████████████████████████████████████████████████████│
        └────────────────────────────────────────────────────┘
        
        Setup Costs (7%)
        ┌──────┐
        │██████│
        └──────┘
```

---

## Per-Agent Cost Calculator

### Inputs

| Parameter | Value | Notes |
|-----------|-------|-------|
| Agent complexity | [Simple/Standard/Complex] | See quick reference |
| Monthly queries | [number] | Expected usage |
| Data sources | [number] | SharePoint, APIs, databases |
| Integrations | [number] | ERP, CRM, custom systems |
| Markets/regions | [number] | Deployment scope |

### Calculation

```
Base Cost = Complexity Cost × Markets
Token Cost = (Monthly Queries × Avg Tokens) × Token Rate
Integration Cost = Integrations × €200/month
Support Cost = Base Cost × 15%

Monthly Agent Cost = Base + Token + Integration + Support
```

### Example: Order Status Agent

| Parameter | Value |
|-----------|-------|
| Complexity | Simple |
| Monthly queries | 50,000 |
| Data sources | 2 (ERP, CRM) |
| Integrations | 1 |
| Markets | 3 |

| Cost Component | Calculation | Monthly |
|----------------|-------------|---------|
| Base cost | €1,450 × 3 | €4,350 |
| Token cost | 50K × 500 × €0.00001 | €250 |
| Integration cost | 1 × €200 | €200 |
| Support cost | €4,350 × 15% | €653 |
| **Total** | | **€5,453** |

---

## ROI Framework

### Efficiency Targets

| Scenario | Efficiency Gain | Value per Market | 28 Markets |
|----------|-----------------|------------------|------------|
| Conservative | 10% | €200K/year | €5.6M/year |
| Target | 20% | €400K/year | €11.2M/year |
| Optimistic | 30% | €600K/year | €16.8M/year |

### Payback Calculation

```
Year 1 Investment: €888K
Target Annual Value: €11.2M (at full scale)
Phase 1 Value (3 markets): €1.2M

Payback Period: 6-12 months (after Phase 2 scale)
```

---

## Chargeback Model

### Principles

1. **Cost transparency:** Track at agent level
2. **Business alignment:** Charge to consuming business units
3. **Incentive design:** Encourage efficient usage
4. **Shared services:** Platform costs allocated proportionally

### Allocation Method

| Cost Type | Allocation Basis |
|-----------|------------------|
| Platform Team | Equal split across business units |
| AIOps Team | Proportional to agent count |
| Azure consumption | Direct attribution by agent |
| Licensing | Per user/seat |

### Example Chargeback

| Business Unit | Agents | Platform Share | Azure | License | Total/Month |
|---------------|--------|----------------|-------|---------|-------------|
| Retail Ops | 5 | €10,000 | €5,000 | €3,000 | €18,000 |
| Supply Chain | 3 | €6,000 | €3,000 | €2,000 | €11,000 |
| Customer Service | 2 | €4,000 | €2,000 | €1,000 | €7,000 |

---

## Cost Optimization Levers

1. **Rightsize SKUs:** Start small, scale based on usage
2. **Token optimization:** Efficient prompts reduce costs 30-50%
3. **Caching:** Cache frequent queries to reduce API calls
4. **Shared infrastructure:** Reuse RAG indexes across agents
5. **Off-peak processing:** Batch non-urgent operations
6. **Regional optimization:** Deploy in cost-effective regions

---

## Budget Request Template

### Phase 1 (3 Months)

| Category | Amount |
|----------|--------|
| One-time setup | €168,000 |
| Operating (3 months) | €180,000 |
| Contingency (15%) | €52,000 |
| **Phase 1 Total** | **€400,000** |

### Full Program (3 Years)

| Year | Amount |
|------|--------|
| Year 1 | €888,000 |
| Year 2 | €720,000 |
| Year 3 | €720,000 |
| **3-Year Total** | **€2,328,000** |

### Incremental Ask

| Item | Amount |
|------|--------|
| New budget required | €1,070,000 |
| Redirected from existing | €1,258,000 |
| **Total program** | **€2,328,000** |

---

*Adjust all figures based on local market rates and organizational context.*

<!-- FORK-NEW: End of fork-specific content -->
