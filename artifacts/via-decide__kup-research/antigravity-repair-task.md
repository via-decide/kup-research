Repair mode for repository via-decide/kup-research.

TARGET
Validate and repair only the files touched by the previous implementation.

TASK
Implement the 'Research Prospectus' generator in src/docs/prospectus-gen.js. [span_14](start_span)This module uses the 'Academic Publisher' agent to draft initial abstracts for the three research outputs: Data Drift, the KUTCH-TIRE-ANOMALY dataset, and Data-Centric AI[span_14](end_span). [span_15](start_span)[span_16](start_span)constraints: Ensure the output highlights how KUP beats the 95% failure rate by focusing on data quality over model complexity[span_15](end_span)[span_16](end_span).

RULES
1. Audit touched files first and identify regressions.
2. Preserve architecture and naming conventions.
3. Make minimal repairs only; do not expand scope.
4. Re-run checks and provide concise root-cause notes.
5. Return complete contents for changed files only.

SOP: REPAIR PROTOCOL (MANDATORY)
1. Strict Fix Only: Do not use repair mode to expand scope or add features.
2. Regression Check: Audit why previous attempt failed before proposing a fix.
3. Minimal Footprint: Only return contents for the actual repaired files.

REPO CONTEXT
- README snippet:
# kup-research
- AGENTS snippet:
not found
- package.json snippet:
not found