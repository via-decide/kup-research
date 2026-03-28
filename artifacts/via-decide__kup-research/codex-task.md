You are working in repository via-decide/kup-research on branch main.

MISSION
Design Research Output 1: Data Drift in Extreme Climate Environments. Define the study design: Train model on Week 1-2 simulated data (20°C baseline), then test Week 3-4 on simulated data at 48°C + humidity variation. Measure six data quality dimensions (from PDF): completeness, feature accuracy, target accuracy, consistent representation, uniqueness, target class balance. For each dimension, measure: (a) how it drifts with temperature/time, (b) how it affects model accuracy, (c) which mitigation strategy (drift detection, noisy training, adaptive models) works best.

CONSTRAINTS
Paper must be submission-ready by Week 4. Results must show quantitative improvements (e.g., drift detection reduces accuracy collapse from 30% to 15%). Include open-source code release (GitHub + Hugging Face).

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