Branch: simba/build-the-benchmark-leaderboard-in-srcwebleaderb
Title: Build the 'Benchmark Leaderboard' in src/web/leaderboard-api.js. Crea...

## Summary
- Repo orchestration task for via-decide/kup-research
- Goal: Build the 'Benchmark Leaderboard' in src/web/leaderboard-api.js. Create an automated evaluation pipeline that accepts model weights from external researchers and calculates their accuracy against your extreme-climate noise scenarios.

## Testing Checklist
- [ ] Run unit/integration tests
- [ ] Validate command flow
- [ ] Validate generated artifact files

## Risks
- Prompt quality depends on repository metadata completeness.
- GitHub API limits/token scope can block deep inspection.

## Rollback
- Revert branch and remove generated artifact files if workflow output is invalid.