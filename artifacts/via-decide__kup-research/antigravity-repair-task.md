Repair mode for repository via-decide/kup-research.

TARGET
Validate and repair only the files touched by the previous implementation.

TASK
Implement the 'NeurIPS Submission Suite' in src/publish/neurips-draft.js. [span_5](start_span)[span_6](start_span)Use the Vora LLM to draft the "Methodology" section, focusing on how the system handled the "Scenario 2" environmental chaos[span_5](end_span)[span_6](end_span). [span_7](start_span)[span_8](start_span)constraints: The draft must include benchmarks comparing the KUP data-centric approach against generic LLM "interface illusions"[span_7](end_span)[span_8](end_span). [span_9](start_span)Ensure the 10K+ dataset downloads from Hugging Face are cited as the validation foundation[span_9](end_span).

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