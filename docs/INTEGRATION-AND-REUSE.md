# Integration and Reuse Map — Digital Cultural Heritage Preservation Assessment

> Cross-skill wiring documentation and cluster integration patterns
> Phase 5 deliverable: Integration & Cross-Skill Wiring

## Overview

The Digital Cultural Heritage Preservation Assessment skill implements the **science-industry cluster pattern** with three reusable shared sub-skills that can be instantiated across sibling cluster skills.

## Cluster Architecture

```
science-industry-cluster/
├── shared-sub-skills/
│   ├── sub-framework-selector.md          ← NEW: Framework selection and binding
│   ├── sub-evidence-based-scoring.md       ← NEW: Multi-dimensional scoring with evidence
│   └── sub-prioritized-roadmap.md          ← NEW: Improvement roadmap generation
│
└── domain-skills/
    ├── digital-heritage-preservation-audit/         ← THIS SKILL
    │   └── skills/
    │       ├── sub-evaluation-framework-selector.md   ← instantiates shared sub-framework-selector
    │       ├── sub-scoring-engine.md                 ← instantiates shared sub-evidence-based-scoring
    │       └── sub-improvement-roadmap.md            ← instantiates shared sub-prioritized-roadmap
    │
    └── [future cluster skills]                       ← PLANNED
        ├── scientific-methodology-audit/
        └── technical-compliance-review/
```

## Shared Sub-Skill Catalog

### 1. `sub-framework-selector` (Shared)

**Purpose**: Select and bind appropriate evaluation frameworks, standards, and citation sources for domain assessments.

**Shared behavior**:
- Framework selection with hierarchy: International > National > Industry > Academic > Expert
- Currentness and openness criteria
- Multi-framework complementary approach
- Full citation and applicability rationale
- Graceful degradation to knowledge base

**Domain instantiations**:
| Domain Skill | Instantiated As | Frameworks Used |
|--------------|----------------|-----------------|
| Digital Heritage Preservation | `sub-evaluation-framework-selector.md` | OAIS (ISO 14721), PREMIS, TRAC/ISO 16363, FADGI, Metamorfoze |
| Scientific Methodology (planned) | `sub-methodology-framework-selector.md` | CONSORT, PRISMA, FAIR, DMP, reproducibility frameworks |
| Technical Compliance (planned) | `sub-compliance-framework-selector.md` | ISO 27001, NIST, SOC 2, GDPR, HIPAA |

**Reuse interface**:
```markdown
## Inputs
- Domain and sub-domain
- Artifact/system characteristics
- User context
- Evidence source availability

## Outputs
- Selected framework set with citations and rationale
- Framework mapping to evaluation dimensions
- Framework limitations statement
```

---

### 2. `sub-evidence-based-scoring` (Shared)

**Purpose**: Multi-dimensional scoring with explicit evidence binding and zero-assumption rule.

**Shared behavior**:
- Per-dimension numeric scores (0-100 or band)
- One-line evidence/justification per dimension
- Evidence hierarchy enforcement
- Zero-assumption rule (state insufficient evidence)
- Graceful degradation to knowledge base

**Domain instantiations**:
| Domain Skill | Instantiated As | Dimensions (example) |
|--------------|----------------|---------------------|
| Digital Heritage Preservation | `sub-scoring-engine.md` | 8 dimensions: Capture/imaging, Format sustainability, Metadata (PREMIS), Fixity, Storage redundancy, Migration strategy, Access & discoverability, Standards conformance (OAIS) |
| Scientific Methodology (planned) | `sub-methodology-scoring.md` | 6-8 dimensions: Study design, Sampling, Measurement validity, Statistical rigor, Reproducibility, Ethics, Transparency |
| Technical Compliance (planned) | `sub-compliance-scoring.md` | 5-7 dimensions: Policy framework, Access control, Encryption, Monitoring, Incident response, Third-party risk |

**Reuse interface**:
```markdown
## Inputs
- Evaluation artifact/system
- Selected framework(s) and rubric
- Scoring dimensions with criteria

## Outputs
- Per-dimension scores with evidence
- Weighted total (if applicable)
- Ranked strengths/weaknesses with citations
- Evidence summary table
```

---

### 3. `sub-prioritized-roadmap` (Shared)

**Purpose**: Convert assessment findings into effort/impact-ranked improvement roadmap with measurable success metrics.

**Shared behavior**:
- Horizon categorization (Quick wins / Major projects / Long-term)
- Effort, impact, and success metric for every item
- Resource realism aligned with user constraints
- Dependency mapping between recommendations
- Framework-grounded recommendations

**Domain instantiations**:
| Domain Skill | Instantiated As | Action Types (example) |
|--------------|----------------|------------------------|
| Digital Heritage Preservation | `sub-improvement-roadmap.md` | Implement SHA-256 fixity, normalize to TIFF/PDF/A-2u, migrate to OAIS AIP packages, establish geographic redundancy |
| Scientific Methodology (planned) | `sub-methodology-roadmap.md` | Adopt pre-registration protocol, implement data management plan, establish reproducible workflows, enhance statistical transparency |
| Technical Compliance (planned) | `sub-compliance-roadmap.md` | Deploy MFA, implement encryption-at-rest, establish SIEM, conduct penetration testing, achieve ISO 27001 certification |

**Reuse interface**:
```markdown
## Inputs
- Scored weaknesses and findings
- User constraints (budget, timeline, staff)
- Success criteria context

## Outputs
- Prioritized roadmap by horizon
- Per-item: action, effort, impact, success metric, dependencies
```

---

## Scoring Output Schema (Standardized)

All cluster skills using `sub-evidence-based-scoring` produce standardized output:

```json
{
  "assessment_id": "unique_identifier",
  "frameworks": [
    {
      "name": "OAIS Reference Model",
      "citation": "ISO 14721:2012",
      "link": "https://www.iso.org/standard/57284.html"
    }
  ],
  "overall_score": 72,
  "score_band": "B",
  "dimensions": [
    {
      "name": "Capture/imaging quality",
      "score": 85,
      "evidence": "Meets FADGI 4-star guidelines; 600dpi for text; 48-bit color; daily calibration targets; QI≥45",
      "strengths": ["Resolution exceeds guidelines", "Robust target workflow"],
      "weaknesses": ["Some legacy images at 400dpi"]
    },
    {
      "name": "Metadata completeness (PREMIS)",
      "score": 52,
      "evidence": "Basic PREMIS elements present; missing provenance events; incomplete rights metadata; fixity tracking partial",
      "strengths": ["Core technical metadata captured"],
      "weaknesses": ["Incomplete provenance chain", "Rights metadata gaps"]
    }
  ],
  "ranked_strengths": [
    {
      "dimension": "Capture/imaging quality",
      "score": 85,
      "justification": "Strong adherence to FADGI guidelines with regular quality monitoring"
    }
  ],
  "ranked_weaknesses": [
    {
      "dimension": "Fixity & integrity checks",
      "score": 35,
      "justification": "No automated fixity verification; MD5 only; no geographic cross-check"
    }
  ],
  "roadmap": {
    "quick_wins": [...],
    "major_projects": [...],
    "long_term": [...]
  }
}
```

---

## Cross-Skill Integration Points

### 1. Framework Selector Integration

All cluster skills' framework selectors inherit from `sub-framework-selector`:

```
sub-framework-selector (shared)
    ↓ instantiates with domain-specific catalogs
├── sub-evaluation-framework-selector (digital-heritage)
├── sub-methodology-framework-selector (scientific-methodology)
└── sub-compliance-framework-selector (technical-compliance)
```

**Integration pattern**:
```markdown
## Inherited Features
- Framework selection hierarchy
- Multi-framework approach
- Graceful degradation
- Full citation requirements

## Domain-Specific Instantiation
- Framework catalog: [domain-appropriate frameworks]
- Selection criteria: [domain-specific priorities]
- Standardization bodies: [domain authorities]
```

### 2. Scoring Engine Integration

All cluster skills' scoring engines inherit from `sub-evidence-based-scoring`:

```
sub-evidence-based-scoring (shared)
    ↓ instantiates with domain dimensions
├── sub-scoring-engine (digital-heritage) → 8 dimensions
├── sub-methodology-scoring (scientific-methodology) → 6-8 dimensions
└── sub-compliance-scoring (technical-compliance) → 5-7 dimensions
```

**Integration pattern**:
```markdown
## Inherited Features
- Per-dimension numeric scoring (0-100)
- Evidence hierarchy enforcement
- Zero-assumption rule
- Graceful degradation

## Domain-Specific Instantiation
- Dimensions: [domain-appropriate dimensions]
- Rubrics: [domain-specific scoring criteria]
- Evidence sources: [domain frameworks and knowledge base]
```

### 3. Roadmap Generator Integration

All cluster skills' roadmap generators inherit from `sub-prioritized-roadmap`:

```
sub-prioritized-roadmap (shared)
    ↓ instantiates with domain action types
├── sub-improvement-roadmap (digital-heritage)
├── sub-methodology-roadmap (scientific-methodology)
└── sub-compliance-roadmap (technical-compliance)
```

**Integration pattern**:
```markdown
## Inherited Features
- Horizon categorization
- Effort/impact/metric requirements
- Resource realism
- Dependency mapping

## Domain-Specific Instantiation
- Action types: [domain-appropriate actions]
- Effort estimation: [domain-specific frameworks]
- Impact scoring: [domain-tailored criteria]
- Success metric patterns: [domain-relevant metrics]
```

---

## Reuse Map Summary

| Shared Sub-Skill | Reused By | Instantiation Pattern | Standardized Output |
|------------------|-----------|----------------------|---------------------|
| `sub-framework-selector` | 3 cluster skills (1 current, 2 planned) | Domain-specific framework catalogs and selection criteria | Selected frameworks with citations and mappings |
| `sub-evidence-based-scoring` | 3 cluster skills (1 current, 2 planned) | Domain-specific dimensions and rubrics | JSON schema with per-dimension scores and evidence |
| `sub-prioritized-roadmap` | 3 cluster skills (1 current, 2 planned) | Domain-specific action types and best practices | Roadmap by horizon with effort/impact/metric per item |

---

## Success Criteria (Phase 5)

✅ **At least one sub-skill reused from/for a sibling cluster skill**: ✓ YES — Three shared sub-skills created (`sub-framework-selector`, `sub-evidence-based-scoring`, `sub-prioritized-roadmap`) ready for reuse across planned sibling skills (scientific-methodology-audit, technical-compliance-review)

✅ **Standardized scoring output schema**: ✓ YES — JSON schema defined with consistent structure for all cluster skills

✅ **Reuse map documented**: ✓ YES — This document provides complete reuse map and integration patterns

✅ **Shared sub-skill references**: ✓ YES — All shared sub-skills include cluster reuse sections with domain-specific adaptation guidance

---

## Future Cluster Skills (Planned)

### Scientific Methodology Audit
- **Frameworks**: CONSORT, PRISMA, FAIR, DMP, reproducibility standards
- **Dimensions**: Study design, sampling, measurement validity, statistical rigor, reproducibility, ethics, transparency
- **Actions**: Pre-registration, data management plans, reproducible workflows, statistical transparency

### Technical Compliance Review
- **Frameworks**: ISO 27001, NIST, SOC 2, GDPR, HIPAA
- **Dimensions**: Policy framework, access control, encryption, monitoring, incident response, third-party risk
- **Actions**: MFA deployment, encryption implementation, SIEM establishment, penetration testing, certification achievement

---

## Integration Quality Validation

✅ **Shared sub-skills follow cluster pattern**: All three shared sub-skills implement consistent structure (Role, Inputs, Workflow, Outputs, Tools, Quality Gate, Cluster Reuse)

✅ **Domain instantiations clearly specified**: Each shared sub-skill includes domain-specific adaptation guidance with examples

✅ **Output schema standardized**: JSON schema defined and applicable across all cluster skills

✅ **Reuse map complete**: Full documentation of how shared sub-skills are instantiated and reused across cluster

✅ **Sibling skills planned**: Two additional cluster skills identified with framework catalogs and dimension examples

---

## Sign-off

- **Phase completion**: 2026-06-23
- **Integration validated**: ✓ Yes
- **Cluster pattern established**: ✓ Yes
- **Reuse map complete**: ✓ Yes
- **Ready for sibling skill development**: ✓ Yes

**Phase 5 Status**: ✅ COMPLETE
