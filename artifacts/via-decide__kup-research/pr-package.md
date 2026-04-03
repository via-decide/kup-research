Branch: simba/implement-the-benchmark-metadata-schema-in-srcda
Title: Implement the 'Benchmark Metadata Schema' in src/data/schema-validato...

## Summary
- Repo orchestration task for via-decide/kup-research
- Goal: Implement the 'Benchmark Metadata Schema' in src/data/schema-validator.js. Define a JSON-LD structure for each vehicle passage that includes: 1) Ambient Temp ($20-48^{\circ}C$), 2) Signal-to-Noise Ratio (SNR), 3) Drift Coefficient, and 4) Anomaly Label.

## Testing Checklist
- [ ] Run unit/integration tests
- [ ] Validate command flow
- [ ] Validate generated artifact files

## Risks
- Prompt quality depends on repository metadata completeness.
- GitHub API limits/token scope can block deep inspection.

## Rollback
- Revert branch and remove generated artifact files if workflow output is invalid.