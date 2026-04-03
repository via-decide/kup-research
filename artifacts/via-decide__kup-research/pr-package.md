Branch: simba/execute-the-final-paper-submission-logic-in-srcp
Title: Execute the 'Final Paper Submission' logic in src/publish/academic-ga...

## Summary
- Repo orchestration task for via-decide/kup-research
- Goal: Execute the 'Final Paper Submission' logic in src/publish/academic-gate.js. Finalize the abstract for 'Sovereign Drift Recovery: Resilience at 48°C and 1M Passages.'

## Testing Checklist
- [ ] Run unit/integration tests
- [ ] Validate command flow
- [ ] Validate generated artifact files

## Risks
- Prompt quality depends on repository metadata completeness.
- GitHub API limits/token scope can block deep inspection.

## Rollback
- Revert branch and remove generated artifact files if workflow output is invalid.