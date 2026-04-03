Branch: simba/implement-the-benchmark-exporter-in-srcdatabench
Title: Implement the 'Benchmark Exporter' in src/data/benchmark-generator.js...

## Summary
- Repo orchestration task for via-decide/kup-research
- Goal: Implement the 'Benchmark Exporter' in src/data/benchmark-generator.js. Create a service that aggregates validated sensor passages from the digital twin into a standardized Parquet format. [span_7](start_span)constraints: Every entry must include metadata for the three "Scenario 2" pollution levels (None, Moderate, Extreme)[span_7](end_span). Use the Sovereign theme to log the real-time progress of the 1M passage export to the terminal.

## Testing Checklist
- [ ] Run unit/integration tests
- [ ] Validate command flow
- [ ] Validate generated artifact files

## Risks
- Prompt quality depends on repository metadata completeness.
- GitHub API limits/token scope can block deep inspection.

## Rollback
- Revert branch and remove generated artifact files if workflow output is invalid.