You are working in repository via-decide/kup-research on branch main.

MISSION
Create the 'Peer Review' Agent Template in src/templates/peer-reviewer.json. Configure the system prompt to critique Research Output 1 (Data Drift) using AAAI/NeurIPS submission criteria.

CONSTRAINTS
The agent must specifically look for "Scenario 2" collapse data and verify that the 1M synthetic vehicle passages from the benchmark are cited correctly. It should refuse to approve any paper that doesn't clearly explain why data-centric AI outperformed model complexity.

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