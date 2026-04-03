Branch: simba/implement-the-research-prospectus-generator-in-s
Title: Implement the 'Research Prospectus' generator in src/docs/prospectus-...

## Summary
- Repo orchestration task for via-decide/kup-research
- Goal: Implement the 'Research Prospectus' generator in src/docs/prospectus-gen.js. [span_14](start_span)This module uses the 'Academic Publisher' agent to draft initial abstracts for the three research outputs: Data Drift, the KUTCH-TIRE-ANOMALY dataset, and Data-Centric AI[span_14](end_span). [span_15](start_span)[span_16](start_span)constraints: Ensure the output highlights how KUP beats the 95% failure rate by focusing on data quality over model complexity[span_15](end_span)[span_16](end_span).

## Testing Checklist
- [ ] Run unit/integration tests
- [ ] Validate command flow
- [ ] Validate generated artifact files

## Risks
- Prompt quality depends on repository metadata completeness.
- GitHub API limits/token scope can block deep inspection.

## Rollback
- Revert branch and remove generated artifact files if workflow output is invalid.