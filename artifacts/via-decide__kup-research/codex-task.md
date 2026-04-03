You are working in repository via-decide/kup-research on branch main.

MISSION
Implement the 'Benchmark Metadata Schema' in src/data/schema-validator.js. Define a JSON-LD structure for each vehicle passage that includes: 1) Ambient Temp ($20-48^{\circ}C$), 2) Signal-to-Noise Ratio (SNR), 3) Drift Coefficient, and 4) Anomaly Label.

CONSTRAINTS
Every passage must be tagged with a "Scenario 2" pollution level. The 'Academic Publisher' agent must validate that the schema complies with AAAI/NeurIPS dataset submission standards.

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