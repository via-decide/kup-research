Branch: simba/create-the-methodology-architect-in-srcpublishme
Title: Create the 'Methodology Architect' in src/publish/methodology-gen.js....

## Summary
- Repo orchestration task for via-decide/kup-research
- Goal: Create the 'Methodology Architect' in src/publish/methodology-gen.js. This module must pull the $D_{KL}$ divergence scores and the Kalman Gain $(\mathbf{K}_k)$ charts from the current chaos simulation.

## Testing Checklist
- [ ] Run unit/integration tests
- [ ] Validate command flow
- [ ] Validate generated artifact files

## Risks
- Prompt quality depends on repository metadata completeness.
- GitHub API limits/token scope can block deep inspection.

## Rollback
- Revert branch and remove generated artifact files if workflow output is invalid.