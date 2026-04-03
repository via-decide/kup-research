Repair mode for repository via-decide/kup-research.

TARGET
Validate and repair only the files touched by the previous implementation.

TASK
Implement the 'Benchmark Exporter' in src/data/benchmark-generator.js. Create a service that aggregates validated sensor passages from the digital twin into a standardized Parquet format. [span_7](start_span)constraints: Every entry must include metadata for the three "Scenario 2" pollution levels (None, Moderate, Extreme)[span_7](end_span). Use the Sovereign theme to log the real-time progress of the 1M passage export to the terminal.

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