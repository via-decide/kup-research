Branch: simba/implement-the-bias-comparator-in-srcanalyticsdis
Title: Implement the 'Bias Comparator' in src/analytics/distribution-check.p...

## Summary
- Repo orchestration task for via-decide/kup-research
- Goal: Implement the 'Bias Comparator' in src/analytics/distribution-check.py. Use the Kullback-Leibler (KL) Divergence formula to measure the difference between the Digital Twin's tire-pressure distribution ($P$) and the physical NHAI sensor baseline ($Q$).

## Testing Checklist
- [ ] Run unit/integration tests
- [ ] Validate command flow
- [ ] Validate generated artifact files

## Risks
- Prompt quality depends on repository metadata completeness.
- GitHub API limits/token scope can block deep inspection.

## Rollback
- Revert branch and remove generated artifact files if workflow output is invalid.