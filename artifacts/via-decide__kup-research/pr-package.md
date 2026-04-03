Branch: simba/build-the-grant-architect-agent-template-in-srct
Title: Build the 'Grant Architect' Agent Template in src/templates/grant-arc...

## Summary
- Repo orchestration task for via-decide/kup-research
- Goal: Build the 'Grant Architect' Agent Template in src/templates/grant-architect.json. [cite_start]Configure the LLM to pull real-world blowout prevention data and KUTCH-TIRE-ANOMALY citation metrics to draft formal grant applications for MeitY or NHAI. [cite: 18-19, 43]

## Testing Checklist
- [ ] Run unit/integration tests
- [ ] Validate command flow
- [ ] Validate generated artifact files

## Risks
- Prompt quality depends on repository metadata completeness.
- GitHub API limits/token scope can block deep inspection.

## Rollback
- Revert branch and remove generated artifact files if workflow output is invalid.