# Fork Changes Tracking

**Fork:** `MattiasNordgren/m365-agents-retail`  
**Upstream:** `nordgren/m365-agents-retail`  
**Last Sync:** 2026-05-31 (tag: `upstream-sync-2026-05-31`)

---

## Purpose

This document tracks all changes made in this fork that differ from the upstream repository. When upstream is updated, use this document to:

1. Identify which fork changes need to be preserved
2. Re-evaluate changes against new upstream content
3. Reapply changes that are still relevant

---

## Change Categories

| Category | Marker | Description |
|----------|--------|-------------|
| **NEW** | `[FORK-NEW]` | New files added in fork, not in upstream |
| **MODIFIED** | `[FORK-MOD]` | Sections modified in existing upstream files |
| **ENHANCED** | `[FORK-ENH]` | Content enhanced with real-world examples |

---

## New Files (FORK-NEW)

Files that exist only in this fork:

| File | Added | Description | Reapply Priority |
|------|-------|-------------|------------------|
| `FORK-CHANGES.md` | 2026-05-31 | This tracking document | HIGH - always keep |
| `CASE-STUDY-RETAIL.md` | 2026-05-31 | Anonymized implementation case study | HIGH |
| `PHASE-0-CHECKLIST.md` | 2026-05-31 | 6-week foundation checklist | HIGH |
| `COST-MODEL-TEMPLATE.md` | 2026-05-31 | Per-agent cost calculator | MEDIUM |

---

## Modified Sections (FORK-MOD)

Changes to existing upstream files. Each change is marked in the file with `<!-- FORK-MOD: description -->` comments.

### AI-MATURITY-MODEL.md

| Section | Change Type | Description |
|---------|-------------|-------------|
| §5.1 Current-State Assessment | FORK-ENH | Added real-world scoring example (3.7/5.0) |
| §5.2 Scoring Process | FORK-MOD | Added "quick-win vs blocker" prioritization |
| §6 Target-State Roadmap | FORK-ENH | Added specific 6-week Phase 0 timeline |

### M365-AGENTS-ARCHITECTURE.md

| Section | Change Type | Description |
|---------|-------------|-------------|
| §4.2 Pattern B Details | FORK-ENH | Added cost model example (€720K/year + €168K setup) |
| §4.2 Pattern B Details | FORK-ENH | Added constrained-retail launch baseline (B2B + IGA + CIAM, native multitenant as future optimization) |
| §8.1 Team Structure | FORK-MOD | Added specific sizing guidance (6 FTE core + 12 federated) |
| §NEW Critical Path | FORK-NEW | Added critical path dependencies section |
| §NEW ROI Timeline | FORK-ENH | Added Fall 2026 agentic commerce example |

### ORG-GOVERNANCE.md

| Section | Change Type | Description |
|---------|-------------|-------------|
| §3.2 Organizational Structure | FORK-ENH | Added Hybrid CoE concrete example with RACI |
| §9.1 Decision Rights | FORK-MOD | Added "Platform Team blocker" as anti-pattern |
| §3.3 CoE Roles | FORK-ENH | Added AIOps staffing guidance (2 FTEs) |
| §NEW FinOps Section | FORK-NEW | Added chargeback model example |

---

## Upstream Sync Procedure

When upstream (`nordgren/m365-agents-retail`) is updated:

```bash
# 1. Fetch upstream changes
git fetch upstream

# 2. View what changed upstream since last sync
git log upstream-sync-2026-05-31..upstream/main --oneline

# 3. Create a branch for the merge
git checkout -b merge-upstream-YYYY-MM-DD

# 4. Merge upstream (will show conflicts in FORK-MOD sections)
git merge upstream/main

# 5. For each conflict:
#    - Check FORK-CHANGES.md for the change description
#    - Decide: keep fork change, take upstream, or merge both
#    - Remove conflict markers

# 6. Re-validate FORK-MOD markers are still present
grep -r "FORK-MOD" *.md

# 7. Update this document with new sync date
# 8. Create new sync tag
git tag -a upstream-sync-YYYY-MM-DD -m "Sync with upstream"

# 9. Push changes
git push origin main --tags
```

---

## Change Log

### 2026-05-31: Initial Fork Customization

**Context:** Applied learnings from IKEA M365 Agents Phase 0 implementation.

**Changes Made:**
1. Added `CASE-STUDY-RETAIL.md` - anonymized implementation case study
2. Added `PHASE-0-CHECKLIST.md` - 6-week foundation checklist
3. Added `COST-MODEL-TEMPLATE.md` - per-agent cost calculator
4. Enhanced AI-MATURITY-MODEL.md with real-world scoring example
5. Enhanced M365-AGENTS-ARCHITECTURE.md with cost model and team sizing
6. Enhanced ORG-GOVERNANCE.md with Hybrid CoE example and AIOps guidance

**Validation:** Changes based on 6-week Phase 0 project with:
- 3.7/5.0 maturity score achieved
- Pattern B architecture selected
- Hybrid CoE (6 FTE core + 12 federated) designed
- €2.33M 3-year business case approved

---

### 2026-06-25: Identity Baseline Clarification from Additional IAM Sources

**Context:** Added more detailed retail IAM source material covering access model, role assignment, D365 authorization, and naming conventions.

**Changes Made:**
1. Enhanced `M365-AGENTS-ARCHITECTURE.md` with a constrained-retail Pattern B baseline
2. Enhanced `CASE-STUDY-RETAIL.md` to show B2B + IGA + CIAM separation as the launch pattern
3. Updated `PHASE-0-CHECKLIST.md` to validate tenant type, coworker/user-type paths, CIAM, and IGA boundaries during Week 3

**Validation:** New source material confirmed that the Phase 0 architecture direction is sufficient for pilot planning, but customer CIAM and entitlement standards remain explicit dependencies before implementation sign-off.

---

## File Markers Reference

All fork-specific content is marked for easy identification:

```markdown
<!-- FORK-NEW: Start of fork-only section -->
... new content ...
<!-- FORK-NEW: End -->

<!-- FORK-MOD: Description of change -->
... modified content ...
<!-- FORK-MOD: End -->

<!-- FORK-ENH: Added real-world example from retail implementation -->
... enhanced content ...
<!-- FORK-ENH: End -->
```

Use `grep -r "FORK-" *.md` to find all fork changes.

---

## Questions for Re-evaluation

When syncing with upstream, ask:

1. **Does upstream now cover this?** If upstream added similar content, consider removing fork change.
2. **Is the fork change still accurate?** Technology moves fast; validate examples.
3. **Should this go upstream?** If the change is broadly useful, consider PR to upstream.
4. **Is the change organization-specific?** Keep in fork if it's tailored to specific context.
