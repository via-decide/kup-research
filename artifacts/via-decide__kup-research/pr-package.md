Branch: simba/create-the-cold-shard-manager-in-srcdatastorage-
Title: Create the 'Cold-Shard' manager in src/data/storage-optimizer.js. Aut...

## Summary
- Repo orchestration task for via-decide/kup-research
- Goal: Create the 'Cold-Shard' manager in src/data/storage-optimizer.js. Automatically move Parquet shards older than 48 hours to remote storage.

## Testing Checklist
- [ ] Run unit/integration tests
- [ ] Validate command flow
- [ ] Validate generated artifact files

## Risks
- Prompt quality depends on repository metadata completeness.
- GitHub API limits/token scope can block deep inspection.

## Rollback
- Revert branch and remove generated artifact files if workflow output is invalid.