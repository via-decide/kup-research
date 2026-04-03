Branch: simba/create-the-f1-score-validator-in-srcanalyticsval
Title: Create the 'F1-Score Validator' in src/analytics/validator.py. Compar...

## Summary
- Repo orchestration task for via-decide/kup-research
- Goal: Create the 'F1-Score Validator' in src/analytics/validator.py. Compare the Kalman-filtered output against the ground-truth "Scenario 2" labels.

## Testing Checklist
- [ ] Run unit/integration tests
- [ ] Validate command flow
- [ ] Validate generated artifact files

## Risks
- Prompt quality depends on repository metadata completeness.
- GitHub API limits/token scope can block deep inspection.

## Rollback
- Revert branch and remove generated artifact files if workflow output is invalid.