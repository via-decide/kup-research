Branch: simba/build-the-academic-publisher-agent-template-in-s
Title: Build 'The Academic Publisher' Agent Template in src/templates/academ...

## Summary
- Repo orchestration task for via-decide/kup-research
- Goal: Build 'The Academic Publisher' Agent Template in src/templates/academic-publisher.json. Guide founders in formatting drift detection metrics and compiling the KUTCH-TIRE-ANOMALY dataset.

## Testing Checklist
- [ ] Run unit/integration tests
- [ ] Validate command flow
- [ ] Validate generated artifact files

## Risks
- Prompt quality depends on repository metadata completeness.
- GitHub API limits/token scope can block deep inspection.

## Rollback
- Revert branch and remove generated artifact files if workflow output is invalid.