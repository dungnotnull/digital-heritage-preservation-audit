# Test Scenarios — Digital Cultural Heritage Preservation Assessment

These scenarios validate the harness, scoring, gates, and graceful degradation. Minimum 5; adversarial and edge cases included.

## Scenario 1: Full assessment
- **Input:** User submits a complete digital cultural heritage preservation assessment artifact and asks for a full evaluation
- **Expected behavior:** Score every dimension with evidence, highlight capture/imaging quality and format sustainability findings, deliver a prioritized roadmap
- **Frameworks expected in output:** OAIS Reference Model (ISO 14721), PREMIS preservation metadata
- **Quality gates checked:** every dimension scored with evidence; roadmap items measurable.
- **Pass criteria:** output contains a scorecard, evidence per dimension, and a prioritized roadmap; no silent assumptions.
## Scenario 2: Targeted concern
- **Input:** User reports a specific weakness in metadata completeness
- **Expected behavior:** Diagnose the metadata completeness issue against the named framework and return focused, measurable fixes
- **Frameworks expected in output:** OAIS Reference Model (ISO 14721), PREMIS preservation metadata
- **Quality gates checked:** every dimension scored with evidence; roadmap items measurable.
- **Pass criteria:** output contains a scorecard, evidence per dimension, and a prioritized roadmap; no silent assumptions.
## Scenario 3: Benchmark / improvement loop
- **Input:** User wants to compare a revised version against a prior baseline
- **Expected behavior:** Re-score against the same rubric, show the before/after delta per dimension, and update the roadmap
- **Frameworks expected in output:** OAIS Reference Model (ISO 14721), PREMIS preservation metadata
- **Quality gates checked:** every dimension scored with evidence; roadmap items measurable.
- **Pass criteria:** output contains a scorecard, evidence per dimension, and a prioritized roadmap; no silent assumptions.

## Scenario 4: Incomplete input (edge case)
- **Input:** User provides only a vague one-line description with no artifact.
- **Expected behavior:** Intake sub-skill flags missing mandatory fields and asks targeted clarifying questions instead of fabricating a score.
- **Pass criteria:** No score is produced from assumptions; unknowns are explicitly listed.

## Scenario 5: Offline / sources unavailable (graceful degradation)
- **Input:** A normal request, but WebSearch/WebFetch are unavailable.
- **Expected behavior:** Skill falls back to SECOND-KNOWLEDGE-BRAIN.md and clearly states the limitation and reduced confidence.
- **Pass criteria:** Output explicitly signals the degraded mode and still cites internal frameworks.

## Scenario 6: Adversarial - Contradictory requirements (adversarial)
- **Input:** User requests both "maximum security with offline storage" and "global public access with cloud-based services" simultaneously.
- **Expected behavior:** Requirements gatherer flags the contradiction and asks for prioritization; does not silently resolve conflict.
- **Pass criteria:** Contradiction explicitly surfaced; no score produced until clarified.

## Scenario 7: Legacy migration scenario (complex case)
- **Input:** User reports a 15-year-old digitization project with TIFF images on external drives, no fixity checks, minimal metadata, and wants to assess preservation readiness.
- **Expected behavior:** Scoring engine identifies all dimensions at risk, provides specific evidence (no SHA-256 fixity, inadequate PREMIS metadata, single-point storage), and roadmap prioritizes urgent fixes.
- **Pass criteria:** Low scores documented with specific evidence; roadmap includes Quick Wins (add fixity), Major projects (metadata enhancement, storage redundancy), Long-term (format migration planning).

## Scenario 8: Small institution constraints (realistic scenario)
- **Input:** Small regional archive reports limited budget (<$50k/year), small staff (2 FTE), mixed digitization (some at 400dpi, some at 200dpi), and wants pragmatic improvement roadmap.
- **Expected behavior:** Scoring acknowledges context; roadmap prioritizes cost-effective improvements (fixity, metadata standards, format normalization) while noting resource constraints.
- **Pass criteria:** Evidence acknowledges constraints; roadmap items include estimated effort and realistic success metrics.

## Scenario 9: Benchmark before/after (validation scenario)
- **Input:** User submits baseline assessment, implements recommended fixes, and requests re-evaluation to measure improvement.
- **Expected behavior:** Scoring engine maintains same rubric; produces before/after delta for each dimension; roadmap updates with next-phase priorities.
- **Pass criteria:** Delta table shows numeric improvement; evidence documents changes; roadmap adapts to new baseline.

## Scenario 10: Multi-repository comparison (advanced scenario)
- **Input:** User wants comparison scoring across three different preservation repositories within their organization to identify best practices and gaps.
- **Expected behavior:** Separate scoring for each repository; comparative analysis highlights differences; cross-pollination roadmap identifies transferable improvements.
- **Pass criteria:** Each repository scored independently; comparative matrix produced; roadmap identifies quick wins from repository-to-repository knowledge transfer.

