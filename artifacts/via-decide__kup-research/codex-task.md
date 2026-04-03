You are working in repository via-decide/kup-research on branch main.

MISSION
Generate the 'High-Frequency Infrastructure Execution' research paper in papers/hfi_execution.md.

CONSTRAINTS
- Document the April orchestration burst of 1100 contributions. - Analyze the 18.8 activity/sec execution rate. - Explain the API synchronization stall caused by billing telemetry lag. - Include mathematical model for orchestration entropy: System_entropy = Event_rate × Sync_latency - Provide diagrams explaining data center state reconciliation. - Log "RESEARCH_ARTIFACT: HFI_EXECUTION_PAPER_GENERATED".

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