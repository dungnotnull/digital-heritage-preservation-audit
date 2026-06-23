# Digital Cultural Heritage Preservation Assessment

> A production-grade AI skill for evaluating, scoring, and improving digital preservation workflows against world-renowned frameworks (OAIS, PREMIS, TRAC, FADGI).

[![Phase Status](https://img.shields.io/badge/Phase-Production%20Ready-success)]()
[![Skill ID](https://img.shields.io/badge/Skill%20ID-97-blue)]()
[![Cluster](https://img.shields.io/badge/Cluster-Science--Industry-purple)]()

## Overview

`digital-heritage-preservation-audit` turns Claude into a digital preservation archivist following OAIS and library-of-record standards. It conducts rigorous, framework-grounded assessments of digitization and preservation workflows, delivering:

- **Multi-dimensional scoring** across 8 preservation dimensions with evidence-based judgments
- **Framework-bound analysis** tied to named, citable standards (OAIS, PREMIS, TRAC, FADGI, Metamorfoze)
- **Prioritized improvement roadmap** with effort/impact/success metrics for every recommendation
- **Self-improving knowledge base** continuously refreshed from authoritative sources

## Target Users & Use Cases

### Primary Users
- **Museum, library, and archive professionals** assessing digitization programs
- **Digital preservation practitioners** evaluating workflow integrity
- **Institutional decision-makers** prioritizing preservation investments
- **Non-experts** seeking expert-grade guidance on preservation best practices

### Trigger Examples
- **Full assessment**: "Evaluate our digital preservation workflow" → Complete 8-dimension scorecard with prioritized roadmap
- **Targeted concern**: "Our metadata seems incomplete" → Focused diagnosis against PREMIS with specific fixes
- **Improvement loop**: "We implemented your recommendations—how much did we improve?" → Before/after delta analysis with updated roadmap

## Quick Start

### Invocation
```bash
/digital-heritage-preservation-audit
```

### Sample Input
```
I need an assessment of our digitization program. We digitize
photographic collections at 400dpi, save as TIFF with minimal
metadata, store on two external hard drives in the same building,
and haven't implemented fixity checks or migration planning.
Our budget is $50k/year with 2 FTE staff.
```

### Sample Output
```
# Digital Preservation Assessment

## Executive Summary
**Overall Score**: 42/100 (Band: D)

**Highest-Leverage Findings**:
1. Critical risk: No fixity verification — silent data loss undetectable
2. Critical risk: Single-point storage (same building) vulnerable to disaster
3. High priority: Incomplete PREMIS metadata limits long-term interpretability

## Scorecard

| Dimension | Score | Evidence/Justification |
|-----------|-------|------------------------|
| Capture/imaging quality | 65/100 | 400dpi meets FADGI 3-star; below 4-star target; no quality targets documented |
| Format sustainability | 50/100 | TIFF sustainable; no format registry; no migration planning |
| Metadata completeness (PREMIS) | 30/100 | Minimal preservation metadata; missing provenance, events, rights |
| Fixity & integrity checks | 15/100 | No fixity verification; integrity not monitored |
| Storage redundancy | 20/100 | Two copies but same location; disaster risk; no geographic distribution |
| Migration strategy | 10/100 | No migration planning; reactive only; format obsolescence risk |
| Access & discoverability | 40/100 | No persistent identifiers; limited discoverability |
| Standards conformance (OAIS) | 35/100 | No AIP packages; informal workflows; minimal documentation |

## Prioritized Improvement Roadmap

### Quick Wins (1-3 months, low effort)
1. **Implement SHA-256 fixity verification**
   - Effort: 2 weeks (1 FTE)
   - Impact: Critical (+30 to Fixity dimension)
   - Success metric: 100% of collection has verified SHA-256 checksums

2. **Adopt PREMIS core metadata elements**
   - Effort: 3 weeks (1 FTE)
   - Impact: High (+20 to Metadata dimension)
   - Success metric: All new digitization includes provenance, events, agents

### Major Projects (3-12 months, moderate-high effort)
1. **Establish geographic storage redundancy**
   - Effort: 2 months ($15k, cloud storage + transfer)
   - Impact: Critical (+40 to Storage dimension)
   - Success metric: 3+ geographic copies with automated fixity cross-check

2. **Develop formal migration strategy**
   - Effort: 3 months (1 FTE + $10k)
   - Impact: High (+30 to Migration dimension)
   - Success metric: 5-year migration plan with technology watch process

### Long-term (1+ years, strategic)
1. **Achieve OAIS conformance**
   - Effort: 12 months (2 FTE + $25k)
   - Impact: Foundational (+40 to Standards conformance)
   - Success metric: Full OAIS AIP packages; submission agreements; preservation planning

## Sources & Frameworks Cited
- OAIS Reference Model (ISO 14721:2012)
- PREMIS Data Dictionary (Library of Congress, 2021)
- FADGI Still Image Benchmark (Library of Congress, 2020)
- NDSA Levels of Preservation (NIST, 2013)
- Format Sustainability Guidelines (Library of Congress Format Registry, 2024)
```

## Evaluation Frameworks

The skill binds all assessments to named, citable frameworks:

| Framework | Standard | Focus |
|----------|----------|-------|
| **OAIS Reference Model** | ISO 14721:2012 | Archival information system architecture |
| **PREMIS** | Library of Congress 2021 | Preservation metadata (provenance, fixity, events, agents, rights) |
| **TRAC** | ISO 16363:2012 | Trustworthy repository audit criteria |
| **FADGI** | Federal Agencies 2020 | Digitization quality benchmarks |
| **Metamorfoze** | National Library of NL 2018 | Preservation imaging quality standards |

## Scoring Dimensions (0-100 scale)

1. **Capture/imaging quality** — Resolution, color depth, quality targets, calibration (FADGI/Metamorfoze)
2. **Format sustainability** — Format risk, openness, migration paths (Library of Congress Format Registry)
3. **Metadata completeness (PREMIS)** — Object characteristics, provenance, events, agents, rights
4. **Fixity & integrity checks** — Hash algorithms, verification frequency, monitoring
5. **Storage redundancy** — Geographic distribution, technology diversity, disaster recovery
6. **Migration strategy** — Planning horizon, technology watch, migration testing
7. **Access & discoverability** — Persistent identifiers, search optimization, rights management
8. **Standards conformance (OAIS)** — AIP packages, submission agreements, preservation planning

## Harness Architecture

```
User Input
    │
    ▼
Intake / Requirements Gathering
    │  → sub-requirements-gatherer
    │     (Capture objectives, stakeholders, constraints, artifact)
    ▼
Framework Selection
    │  → sub-evaluation-framework-selector
    │     (Bind to OAIS, PREMIS, TRAC, FADGI with citations)
    ▼
Multi-Dimensional Scoring
    │  → sub-scoring-engine
    │     (Score 8 dimensions with evidence per dimension)
    ▼
Improvement Roadmap
    │  → sub-improvement-roadmap
    │     (Prioritize Quick wins / Major projects / Long-term)
    ▼
Quality Gates
    │  → Evidence verification
    │  → Framework citation check
    │  → Roadmap measurability check
    │  → Devil's-advocate review
    ▼
DELIVERABLE (Scorecard + Roadmap + Executive Summary)
```

## Quality Gates

All outputs must pass 4 quality gates before presentation:

1. **Evidence gate**: Every scored dimension has explicit evidence tied to a framework
2. **Framework gate**: At least one named, citable framework is referenced
3. **Measurability gate**: Every roadmap item has effort, impact, and a measurable success metric
4. **Advocacy gate**: A devil's-advocate pass challenged the top findings before output

## Self-Improving Knowledge Base

The skill maintains a living knowledge base (`SECOND-KNOWLEDGE-BRAIN.md`) that:

- **Seeds authoritative sources** from Library of Congress, OAIS/CCSDS, DPC, FADGI, ArXiv (cs.DL)
- **Auto-updates weekly** via `tools/knowledge_updater.py` (crawl4ai pipeline)
- **Deduplicates by URL/DOI hash** to avoid redundant entries
- **Scores by recency × relevance** to prioritize high-value findings
- **Stores with citations** (Title, Authors, Year, Venue, DOI/Link, Relevance)

When live sources are unavailable, the skill gracefully degrades to the internal knowledge base and explicitly states the limitation.

## Testing & Validation

All 10 test scenarios pass with 100% quality gate compliance:

| Scenario | Type | Status |
|----------|------|--------|
| Full assessment | Core | ✅ Pass |
| Targeted concern | Core | ✅ Pass |
| Benchmark / improvement loop | Core | ✅ Pass |
| Incomplete input | Edge case | ✅ Pass |
| Offline / sources unavailable | Graceful degradation | ✅ Pass |
| Contradictory requirements | Adversarial | ✅ Pass |
| Legacy migration scenario | Complex | ✅ Pass |
| Small institution constraints | Realistic | ✅ Pass |
| Benchmark before/after | Validation | ✅ Pass |
| Multi-repository comparison | Advanced | ✅ Pass |

See `tests/TEST-EXECUTION-LOG.md` for detailed validation results.

## Cluster Integration

This skill implements the **science-industry cluster pattern** with three reusable shared sub-skills:

1. **`sub-framework-selector`** — Framework selection and binding
2. **`sub-evidence-based-scoring`** — Multi-dimensional scoring with evidence
3. **`sub-prioritized-roadmap`** — Improvement roadmap generation

These shared sub-skills can be instantiated across sibling cluster skills (planned: scientific-methodology-audit, technical-compliance-review).

See `docs/INTEGRATION-AND-REUSE.md` for complete integration documentation.

## Project Structure

```
digital-heritage-preservation-audit/
├── README.md                               # This file
├── CLAUDE.md                               # Project instructions
├── PROJECT-detail.md                       # Technical specification
├── PROJECT-DEVELOPMENT-PHASE-TRACKING.md   # Phase completion status
├── SECOND-KNOWLEDGE-BRAIN.md               # Living knowledge base
├── docs/
│   └── INTEGRATION-AND-REUSE.md           # Cluster integration docs
├── skills/
│   ├── main.md                             # Main harness
│   ├── sub-evaluation-framework-selector.md
│   ├── sub-requirements-gatherer.md
│   ├── sub-scoring-engine.md
│   ├── sub-improvement-roadmap.md
│   └── shared/                             # Cluster shared sub-skills
│       ├── sub-framework-selector.md
│       ├── sub-evidence-based-scoring.md
│       └── sub-prioritized-roadmap.md
├── tools/
│   └── knowledge_updater.py               # crawl4ai pipeline
└── tests/
    ├── test-scenarios.md                   # Test scenario definitions
    └── TEST-EXECUTION-LOG.md              # Validation results
```

## Installation & Setup

### Prerequisites
- Claude Code CLI with skill system support
- (Optional) For knowledge updates: `pip install crawl4ai`

### Installation
1. Clone this repository to your skills directory
2. The skill is automatically available as `/digital-heritage-preservation-audit`
3. (Optional) Schedule weekly knowledge updates: `python tools/knowledge_updater.py`

### Knowledge Update Schedule
```bash
# Manual update
python tools/knowledge_updater.py

# Weekly cron (Linux/Mac)
0 2 * * 0 cd /path/to/skill && python tools/knowledge_updater.py

# Weekly scheduled task (Windows)
schtasks /create /tn "Preservation Knowledge Update" /tr "python D:\path\to\skill\tools\knowledge_updater.py" /sc weekly /d SUN /st 02:00
```

## Development Phases

| Phase | Status | Description |
|-------|--------|-------------|
| Phase 0 | ✅ Complete | Research & skill architecture |
| Phase 1 | ✅ Complete | Core sub-skills implementation |
| Phase 2 | ✅ Complete | Main harness & quality gates |
| Phase 3 | ✅ Complete | Knowledge base pipeline |
| Phase 4 | ✅ Complete | Testing & validation |
| Phase 5 | ✅ Complete | Integration & cross-skill wiring |

**Overall Status**: 100% Complete, Production-Ready

## Contributing

This skill is part of the science-industry cluster. When contributing:

1. **Framework additions**: Add to framework catalogs with full citations
2. **Dimension updates**: Update rubrics in `SECOND-KNOWLEDGE-BRAIN.md`
3. **Test coverage**: Add new scenarios to `tests/test-scenarios.md`
4. **Shared sub-skills**: For cluster-wide changes, update `skills/shared/`

## License

[Open-source license to be determined for public release]

## Acknowledgments

- **Library of Congress** — Digital preservation frameworks and guidelines
- **CCSDS** — OAIS Reference Model (ISO 14721)
- **Digital Preservation Coalition** — Best practices and resources
- **Federal Agencies Digital Guidelines Initiative (FADGI)** — Imaging quality benchmarks
- **National Library of the Netherlands (Metamorfoze)** — Preservation imaging standards

## Citation

If you use this skill in your work, please cite:

```
Digital Cultural Heritage Preservation Assessment Skill (v1.0).
Science-Industry Cluster. 2026.
https://github.com/[repo-url]
```

---

**Version**: 1.0.0-production  
**Last Updated**: 2026-06-23  
**Phase**: Production-ready, open-source release
