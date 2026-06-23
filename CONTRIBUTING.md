# Contributing to Digital Cultural Heritage Preservation Assessment

Thank you for your interest in contributing to this project! This document provides guidelines for contributing to the Digital Cultural Heritage Preservation Assessment skill.

## Project Overview

This skill is part of the **science-industry cluster** and implements framework-grounded, evidence-based assessment of digital preservation workflows. It follows OAIS, PREMIS, TRAC, FADGI, and Metamorfoze standards to evaluate 8 dimensions of digital preservation readiness.

## Development Philosophy

- **Evidence-first**: Every assessment must be grounded in named frameworks and cited evidence
- **Zero assumptions**: Unknowns are surfaced explicitly; never fabricate scores from incomplete information
- **Production-grade**: All code is production-ready; no dummy code, placeholders, or comment-only implementations
- **Graceful degradation**: When external sources unavailable, fall back to knowledge base and state limitations
- **Cluster reusability**: Shared sub-skills follow cluster patterns for sibling skill reuse

## Contribution Areas

### 1. Framework Additions

Add new evaluation frameworks to the framework catalog:

**File to modify**: `skills/sub-evaluation-framework-selector.md` and `SECOND-KNOWLEDGE-BRAIN.md`

**Requirements**:
- Framework must be named and citable (standard number, DOI, official link)
- Framework must be authoritative (international/national standard, industry consensus)
- Framework must include applicability rationale
- Framework must map to specific evaluation dimensions

**Example**:
```markdown
### New Framework
- **Name**: Framework Name (Standard Number)
- **Body**: Standardization body
- **Year**: Publication year
- **Link**: Official URL or DOI
- **Applicability**: When and why this framework applies
- **Dimension mapping**: Which evaluation dimensions this framework informs
```

### 2. Dimension Updates

Update scoring rubrics and criteria for evaluation dimensions:

**File to modify**: `SECOND-KNOWLEDGE-BRAIN.md` section "8. Practical Scoring Criteria"

**Requirements**:
- Maintain 0-100 scale with 5-point bands (90-100, 70-89, 50-69, 30-49, 0-29)
- Provide specific criteria for each band
- Tie criteria to named frameworks where applicable
- Include measurable thresholds

**Example**:
```markdown
#### X. Dimension Name
- **90-100**: Exceeds framework guidelines; specific criteria A, B, C
- **70-89**: Meets framework guidelines; specific criteria D, E, F
- **50-69**: Partial compliance; specific criteria G, H, I
- **30-49**: Below standards; specific criteria J, K, L
- **0-29**: No compliance; specific criteria M, N, O
```

### 3. Test Scenarios

Add new test scenarios to expand coverage:

**File to modify**: `tests/test-scenarios.md`

**Requirements**:
- Include input description, expected behavior, and pass criteria
- Cover new use cases, edge cases, or adversarial scenarios
- Validate specific quality gates or framework bindings
- Update `tests/TEST-EXECUTION-LOG.md` with validation results

**Example**:
```markdown
## Scenario X: [Scenario name]
- **Input**: [User input description]
- **Expected behavior**: [What the skill should do]
- **Frameworks expected in output**: [Which frameworks should apply]
- **Quality gates checked**: [Which gates to validate]
- **Pass criteria**: [Specific success criteria]
```

### 4. Shared Sub-Skills

For cluster-wide changes, update shared sub-skills:

**Directory**: `skills/shared/`

**Files**:
- `sub-framework-selector.md` — Framework selection patterns
- `sub-evidence-based-scoring.md` — Scoring engine patterns
- `sub-prioritized-roadmap.md` — Roadmap generation patterns

**Requirements**:
- Maintain cluster-wide applicability
- Document domain-specific instantiation patterns
- Include cluster reuse examples
- Update integration documentation in `docs/INTEGRATION-AND-REUSE.md`

### 5. Knowledge Base Updates

Contribute to the living knowledge base:

**File to modify**: `SECOND-KNOWLEDGE-BRAIN.md`

**Sections**:
- "2. Key Research Papers" — Add new research with citations
- "3. State-of-the-Art Methods & Tools" — Add new methods and tools
- "8. Practical Scoring Criteria" — Update scoring rubrics
- "9. Common Preservation Anti-Patterns" — Add new anti-patterns

**Requirements**:
- All entries must include citations (Title, Authors, Year, Venue, DOI/Link, Relevance)
- Research papers should follow evidence hierarchy (Systematic Review > Meta-Analysis > RCT/Benchmark > Cohort/Case Study > Expert Opinion > Blog)
- Tools and methods should be production-grade and widely recognized
- Anti-patterns should be common failure modes with clear guidance

## Development Workflow

### 1. Setup

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/your-feature-name`
3. Make your changes following the guidelines above

### 2. Testing

Before submitting:

1. **Test locally**: Run the skill with test scenarios from `tests/test-scenarios.md`
2. **Validate quality gates**: Ensure all 4 quality gates pass
3. **Check documentation**: Verify all documentation is updated
4. **Test shared skills**: If modifying shared sub-skills, verify cluster-wide applicability

### 3. Submission

1. Commit your changes with clear commit messages
2. Push to your fork
3. Create a pull request with:
   - Description of changes
   - Test scenarios covered
   - Documentation updates
   - Quality gate validation results

### 4. Review Process

Maintainers will review for:
- **Framework grounding**: Are all assessments tied to named frameworks?
- **Evidence quality**: Is evidence properly cited and hierarchical?
- **Code quality**: Is code production-grade with no placeholders?
- **Documentation**: Are all changes properly documented?
- **Cluster reusability**: Do shared sub-skills maintain cluster-wide applicability?

## Code Quality Standards

### Production-Grade Requirements

- ✅ **No dummy code**: All implementations must be functional
- ✅ **No comment placeholders**: No TODOs or FIXMEs in production code
- ✅ **Real implementations**: All tools and workflows must be fully implemented
- ✅ **Error handling**: Graceful degradation for offline/failure modes
- ✅ **Documentation**: Comprehensive inline and external documentation

### Style Guidelines

- **Clear naming**: Use descriptive names for files, functions, and variables
- **Modular design**: Clear separation of concerns between harness, sub-skills, and shared components
- **Consistent structure**: Follow existing file structure and naming conventions
- **Frontmatter completeness**: All skill files must include complete frontmatter (name, description)

## Quality Gates

All contributions must pass the 4 quality gates:

### Gate 1: Evidence Gate
- Every scored dimension has explicit evidence
- Evidence is tied to named frameworks
- No unscored dimensions

### Gate 2: Framework Gate
- At least one named, citable framework is referenced
- Framework includes full citation (standard number, DOI, link)
- Framework applicability is documented

### Gate 3: Measurability Gate
- Every roadmap item has effort estimate
- Every roadmap item has impact assessment
- Every roadmap item has measurable success metric

### Gate 4: Advocacy Gate
- Devil's-advocate review completed
- Findings challenged against anti-patterns
- Contradictions surfaced and resolved

## Documentation Standards

### User Documentation

- **README.md**: Overview, quick start, examples
- **PROJECT-detail.md**: Technical specification
- **CHANGELOG.md**: Version history and changes

### Technical Documentation

- **docs/INTEGRATION-AND-REUSE.md**: Cluster integration
- **tests/TEST-EXECUTION-LOG.md**: Test validation
- **SECOND-KNOWLEDGE-BRAIN.md**: Knowledge base

### Skill Documentation

Each skill file must include:
- **Frontmatter**: name, description
- **Role**: Clear purpose and persona
- **Inputs**: All required inputs
- **Workflow**: Step-by-step process
- **Outputs**: All produced outputs
- **Tools**: Required tools
- **Quality Gate**: Validation criteria
- **Notes**: Important considerations

## Cluster Contribution Guidelines

### Shared Sub-Skills

When contributing to shared sub-skills (`skills/shared/`):

1. **Maintain cluster-wide applicability**: Ensure changes work across all cluster skills
2. **Document domain patterns**: Provide examples of domain-specific instantiation
3. **Update integration docs**: Keep `docs/INTEGRATION-AND-REUSE.md` current
4. **Test sibling skills**: Verify changes don't break planned sibling skills

### New Cluster Skills

When proposing new sibling cluster skills:

1. **Follow cluster pattern**: Use shared sub-skills with domain instantiation
2. **Document frameworks**: Provide framework catalog and selection criteria
3. **Define dimensions**: Specify evaluation dimensions and rubrics
4. **Plan integration**: Document how skill integrates with cluster

## Issue Reporting

When reporting issues, include:

1. **Scenario description**: What were you trying to assess?
2. **Input provided**: What information did you give the skill?
3. **Expected behavior**: What should have happened?
4. **Actual behavior**: What actually happened?
5. **Framework expectations**: Which frameworks should apply?
6. **Quality gate issues**: Which quality gates failed (if any)?

## Community Guidelines

- **Respectful collaboration**: Maintain respectful and constructive communication
- **Evidence-based discussions**: Ground discussions in named frameworks and cited evidence
- **Quality-first**: Prioritize production quality over feature breadth
- **Documentation emphasis**: Value comprehensive documentation as highly as code
- **Cluster awareness**: Consider cluster-wide implications of changes

## License

By contributing, you agree that your contributions will be licensed under the same license as the project (to be determined for open-source release).

## Acknowledgments

Contributors will be acknowledged in:
- RELEASE notes for significant contributions
- CONTRIBUTING.md for ongoing contributors
- Specific framework or dimension documentation for specialized contributions

---

Thank you for contributing to the Digital Cultural Heritage Preservation Assessment skill! Your contributions help ensure the long-term accessibility of our digital cultural heritage.
