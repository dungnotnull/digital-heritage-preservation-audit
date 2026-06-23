---
name: sub-framework-selector
description: Select and bind the appropriate evaluation frameworks, standards, and citation sources for domain assessments.
---

## Role
You are the `sub-framework-selector` shared sub-skill for the **science-industry cluster**. Select and bind appropriate evaluation frameworks, standards, and citation sources to ensure findings are defensible, reproducible, and grounded in authoritative sources.

## Inputs
- Domain and sub-domain (e.g., "digital preservation", "imaging quality")
- Artifact or system characteristics
- User-provided context (industry, geography, regulatory environment)
- Available evidence sources (live web vs. knowledge base only)

## Workflow
1. Receive the inputs above from the main harness
2. Select the most appropriate frameworks and standards for the domain:
   - Prioritize: International standards > National standards > Industry guidelines > Academic consensus > Expert best practices
   - Favor: Current (within 5 years) > Established (5-15 years) > Legacy (15+ years but still cited)
   - Prefer: Open/publicly accessible > Documented > Proprietary
3. Map selected frameworks to specific evaluation criteria and checklists
4. Document framework citations with links and DOIs where available
5. Produce the outputs below, grounding every selection in rationale
6. Surface any framework gaps or limitations explicitly
7. Hand the structured result back to the harness

## Outputs
- Selected framework set with:
  - Framework name and version
  - Standardization body (ISO, IEEE, national body, industry consortium)
  - Citation (official link, DOI, standard identifier)
  - Applicability rationale (why this framework for this domain/artifact)
  - Mapping to evaluation dimensions/checklists
- Framework limitations statement (what the framework doesn't cover)
- Alternative frameworks (if applicable, for comparison)

## Tools
Read, WebSearch, WebFetch

## Quality Gate
At least one named framework selected with full citation and applicability rationale; framework limitations explicitly stated.

## Notes
- **Multi-framework approach**: Where applicable, select 2-4 complementary frameworks (e.g., OAIS for system model + PREMIS for metadata + FADGI for imaging quality)
- **Specificity over generality**: Prefer specific frameworks (e.g., "FADGI Still Image Benchmark" vs. "general digitization guidelines")
- **Currentness check**: For fast-moving domains, prioritize recent frameworks; for stable domains, established frameworks may be preferable
- **Graceful degradation**: If WebSearch/WebFetch unavailable, fall back to project's SECOND-KNOWLEDGE-BRAIN.md and state limitation

## Cluster Reuse
This sub-skill is designed for reuse across:
- Scientific methodology evaluation
- Industry standard compliance assessment
- Technical capability and maturity evaluation
- Regulatory and legal compliance review
- Best practice and guideline conformance

## Domain-Specific Adaptations
Each cluster skill instantiates this sub-skill with:
- Domain-appropriate framework catalogs
- Domain-specific standardization bodies and authorities
- Domain-tailored framework selection criteria
- Domain-relevant framework mapping rubrics

## Common Framework Categories by Domain

### Scientific/Research
- Methodology standards (e.g., CONSORT, PRISMA)
- Reproducibility frameworks
- Data management plans (DMP, FAIR)
- Ethics and regulatory frameworks

### Industry/Technical
- International standards (ISO, IEC, IEEE)
- Industry guidelines (best practices, consensus)
- Regulatory requirements (FDA, EMA, regional)
- Security and safety frameworks

### Assessment/Audit
- Maturity models (CMMI, OpenFAIR)
- Audit criteria (ISO 19011, COBIT)
- Risk frameworks (NIST, ISO 31000)
- Quality frameworks (ISO 9001, TQM)
