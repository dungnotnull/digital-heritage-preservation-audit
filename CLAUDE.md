# CLAUDE.md — Digital Cultural Heritage Preservation Assessment

**Skill name:** `digital-heritage-preservation-audit`
**Tagline:** Assess a digitization/preservation workflow for integrity and long-term accessibility.
**Source idea:** #97 (cluster: `science-industry`)
**Current phase:** Phase 4 — Testing & Validation (initial build complete)

## Problem This Skill Solves
Museums, libraries, and archives digitize collections but risk format obsolescence, bit-rot, and metadata loss. They need an audit against recognized preservation standards.

## Harness Flow Summary
1. **sub-evaluation-framework-selector** → Bind the audit to named, citable technical standards so findings are defensible.
2. **sub-requirements-gatherer** → Capture objectives, stakeholders, constraints, and the document/artifact under review so analysis is complete.
3. **sub-scoring-engine** → Produce a transparent, dimension-by-dimension score (0-100 or band) with evidence for every sub-score.
4. **sub-improvement-roadmap** → Convert weaknesses into a sequenced, effort/impact-ranked action plan the user can execute.
5. **main (synthesis)** → assemble the scored deliverable + prioritized roadmap and run final quality gates.

## Gates
No safety/compliance gate applies to this cluster; standard quality gates still apply.

## Sub-skills
- `skills/sub-evaluation-framework-selector.md` — Select the governing digital-preservation standards/heuristics for this evaluation.
- `skills/sub-requirements-gatherer.md` — Elicit and structure the full set of preservation workflow requirements and context.
- `skills/sub-scoring-engine.md` — Multi-dimensional scoring of the preservation workflow against the selected framework.
- `skills/sub-improvement-roadmap.md` — Prioritized improvement roadmap for the preservation with effort/impact.

## Tools Required
WebSearch, WebFetch, Read, Write, Bash

## Knowledge Sources
- [Library of Congress digital preservation](https://www.loc.gov/programs/digital-collections-management/)
- [OAIS / CCSDS](https://public.ccsds.org)
- [Digital Preservation Coalition](https://www.dpconline.org)
- [FADGI](http://www.digitizationguidelines.gov)

ArXiv / research categories crawled: cs.DL

## Supporting Tools
- `tools/knowledge_updater.py` — crawl4ai pipeline that refreshes `SECOND-KNOWLEDGE-BRAIN.md` weekly from the sources above.

## Active Development Tasks
- [x] Scaffold deliverables and sub-skills
- [x] Define scoring dimensions against named frameworks
- [ ] Expand `SECOND-KNOWLEDGE-BRAIN.md` with first crawl batch
- [ ] Add 3 more adversarial test scenarios
- [ ] Wire shared cluster sub-skills for reuse

## Reference Docs
- `PROJECT-detail.md` — full technical spec
- `PROJECT-DEVELOPMENT-PHASE-TRACKING.md` — phase roadmap
- `SECOND-KNOWLEDGE-BRAIN.md` — living domain knowledge base
