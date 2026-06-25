---
title: Home
nav_order: 1
has_toc: false
permalink: /
---

## 📚 Documentation

| Document | Description |
|----------|-------------|
| [**M365-AGENTS-ARCHITECTURE.md**](M365-AGENTS-ARCHITECTURE.md) | Main architecture document (~150KB) — decision trees, patterns, security, operations |
| [**ORG-GOVERNANCE.md**](ORG-GOVERNANCE.md) | Organizational model for franchise retail (~45KB) — CoE structure, TOGAF integration |
| [**AI-MATURITY-MODEL.md**](AI-MATURITY-MODEL.md) | Multi-dimensional maturity assessment (~32KB) — 6 dimensions, 5 levels |
| [**README.md**](README.md) | Quick start and repository overview |

---

## 🎯 Key Topics

### Architecture Patterns

| Pattern | Description | Use Case |
|---------|-------------|----------|
| **Pattern A** | Corporate-only agents | Single tenant, HQ users |
| **Pattern B** | Dual-tenant agents | Enterprise + Retail tenants |
| **Pattern C** | Federated agent mesh | 3+ tenants, franchise model |

### Governance & Security

- Microsoft Agent 365 as native control plane
- Entra Agent ID for agent identity management
- OWASP Top 10 for Agentic AI mapping
- Automated red teaming with PyRIT

### Operations

- Worked cost examples (500 / 5,000 / 15,000 users)
- Operational runbooks (deployment, incident response, cost anomaly)
- Agent development standards (AGENTS.md, SKILL.md patterns)

---

## 📊 Diagrams

**PlantUML** (`/plantuml/`)
- Conceptual architecture
- Dual-tenant integration
- Identity & API patterns
- CI/CD pipeline
- CoE structure
- AI maturity model

**draw.io** (`/diagrams/`)
- Layered architecture overview
- Security architecture
- Governance model
- Maturity heatmap template

---

**Version 3.2** · April 2026 · [View source on GitHub](https://github.com/nordgren/m365-agents-retail)
