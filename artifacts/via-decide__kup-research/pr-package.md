Branch: simba/build-the-passage-sharder-in-srcdatasharding-eng
Title: Build the 'Passage Sharder' in src/data/sharding-engine.js. Implement...

## Summary
- Repo orchestration task for via-decide/kup-research
- Goal: Build the 'Passage Sharder' in src/data/sharding-engine.js. Implement a logic that automatically splits the 1M vehicle passages into 10,000-entry Parquet shards.

## Testing Checklist
- [ ] Run unit/integration tests
- [ ] Validate command flow
- [ ] Validate generated artifact files

## Risks
- Prompt quality depends on repository metadata completeness.
- GitHub API limits/token scope can block deep inspection.

## Rollback
- Revert branch and remove generated artifact files if workflow output is invalid.