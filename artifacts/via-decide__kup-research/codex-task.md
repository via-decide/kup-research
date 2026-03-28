You are working in repository via-decide/kup-research on branch main.

MISSION
Design Research Output 3: Data-Centric AI in Physical Infrastructure. Position the paper as a case study: apply the PDF's 6 data quality dimensions to a real infrastructure system (TPM). Show empirical proof that data quality > model complexity: compare (a) weak model on clean data vs. (b) strong model on noisy data. Document the data pipeline architecture: sensors → edge feature extraction → drift monitoring → cloud model retraining.

CONSTRAINTS
Must include production deployment data (not lab-only results). Open-source reference architecture (Docker + Kubernetes + Kafka templates).

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