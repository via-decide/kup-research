Branch: simba/build-the-abstract-architect-in-srcpublishabstra
Title: Build the 'Abstract Architect' in src/publish/abstract-gen.js. [span_...

## Summary
- Repo orchestration task for via-decide/kup-research
- Goal: Build the 'Abstract Architect' in src/publish/abstract-gen.js. [span_12](start_span)[span_13](start_span)This module uses the 'Academic Publisher' agent to draft paper abstracts specifically highlighting how "Data-Centric AI" defeated temperature drift ($20-48^{\circ}C$) on the highway.[span_12](end_span)[span_13](end_span) [span_14](start_span)constraints: The output must format citations correctly for the 'KUTCH-TIRE-ANOMALY' dataset and reference the 1M vehicle passage benchmark.[span_14](end_span)

## Testing Checklist
- [ ] Run unit/integration tests
- [ ] Validate command flow
- [ ] Validate generated artifact files

## Risks
- Prompt quality depends on repository metadata completeness.
- GitHub API limits/token scope can block deep inspection.

## Rollback
- Revert branch and remove generated artifact files if workflow output is invalid.