Repair mode for repository via-decide/kup-research.

TARGET
Validate and repair only the files touched by the previous implementation.

TASK
Build the 'Abstract Architect' in src/publish/abstract-gen.js. [span_12](start_span)[span_13](start_span)This module uses the 'Academic Publisher' agent to draft paper abstracts specifically highlighting how "Data-Centric AI" defeated temperature drift ($20-48^{\circ}C$) on the highway.[span_12](end_span)[span_13](end_span) [span_14](start_span)constraints: The output must format citations correctly for the 'KUTCH-TIRE-ANOMALY' dataset and reference the 1M vehicle passage benchmark.[span_14](end_span)

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