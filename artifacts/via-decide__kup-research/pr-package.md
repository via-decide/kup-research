Branch: simba/create-the-peer-review-agent-template-in-srctemp
Title: Create the 'Peer Review' Agent Template in src/templates/peer-reviewe...

## Summary
- Repo orchestration task for via-decide/kup-research
- Goal: Create the 'Peer Review' Agent Template in src/templates/peer-reviewer.json. Configure the system prompt to critique Research Output 1 (Data Drift) using AAAI/NeurIPS submission criteria.

## Testing Checklist
- [ ] Run unit/integration tests
- [ ] Validate command flow
- [ ] Validate generated artifact files

## Risks
- Prompt quality depends on repository metadata completeness.
- GitHub API limits/token scope can block deep inspection.

## Rollback
- Revert branch and remove generated artifact files if workflow output is invalid.