Branch: simba/implement-the-dataset-exporter-in-srcdataglobal-
Title: Implement the 'Dataset Exporter' in src/data/global-release.js. Packa...

## Summary
- Repo orchestration task for via-decide/kup-research
- Goal: Implement the 'Dataset Exporter' in src/data/global-release.js. Package the 1M passages into 100 compressed Parquet shards, including the 'Provenance' hardware signatures.

## Testing Checklist
- [ ] Run unit/integration tests
- [ ] Validate command flow
- [ ] Validate generated artifact files

## Risks
- Prompt quality depends on repository metadata completeness.
- GitHub API limits/token scope can block deep inspection.

## Rollback
- Revert branch and remove generated artifact files if workflow output is invalid.