Branch: simba/build-the-provenance-generator-in-srcdatawaterma
Title: Build the 'Provenance Generator' in src/data/watermark.js. Hash the M...

## Summary
- Repo orchestration task for via-decide/kup-research
- Goal: Build the 'Provenance Generator' in src/data/watermark.js. Hash the M4 Mac Mini's Serial Number + the 'Scenario 2' seed to create a unique 'Sovereign ID' for every batch of 1,000 vehicles.

## Testing Checklist
- [ ] Run unit/integration tests
- [ ] Validate command flow
- [ ] Validate generated artifact files

## Risks
- Prompt quality depends on repository metadata completeness.
- GitHub API limits/token scope can block deep inspection.

## Rollback
- Revert branch and remove generated artifact files if workflow output is invalid.