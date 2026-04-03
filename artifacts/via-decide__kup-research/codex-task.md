You are working in repository via-decide/kup-research on branch main.

MISSION
Create the 'Academic LaTeX Generator' in src/docs/latex-gen.js. This script pulls data drift metrics, KUTCH-TIRE-ANOMALY dataset statistics, and "Scenario 2" recovery charts into a pre-formatted AAAI/NeurIPS LaTeX template. [span_9](start_span)constraints: Automatically calculate the $p\text{-value}$ and $R^2$ scores for the temperature-drift correlations ($20-48^{\circ}C$) to ensure scientific rigor[span_9](end_span). The agent must flag any "Data Quality" gaps before finalizing the PDF.

CONSTRAINTS
Preserve existing code; prefer additive changes.

PROCESS (MANDATORY)
1. Read README.md and AGENTS.md before editing.
2. Audit architecture before coding. Summarize current behavior.
3. Preserve unrelated working code. Prefer additive modular changes.
4. Implement the smallest safe change set for the stated goal.
5. Run validation commands and fix discovered issues.
6. Self-review for regressions, missing env wiring, and docs drift.
7. Return complete final file contents for every modified or created file.

REPO AUDIT CONTEXT
- Description: 
- Primary language: unknown
- README snippet:
# kup-research

- AGENTS snippet:
not found


SOP: PRE-MODIFICATION PROTOCOL (MANDATORY)
1. Adherence to Instructions: No deviations without explicit user approval.
2. Mandatory Clarification: Immediately ask if instructions are ambiguous or incomplete.
3. Proposal First: Always propose optimizations or fixes before implementing them.
4. Scope Discipline: Do not add unrequested features or modify unrelated code.
5. Vulnerability Check: Immediately flag and explain security risks.

OUTPUT REQUIREMENTS
- Include: implementation summary, checks run, risks, rollback notes.
- Generate branch + PR package.
- Keep prompts deterministic and preservation-first.