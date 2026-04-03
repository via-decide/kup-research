Branch: simba/build-the-institutional-wiki-in-srcdocsknowledge
Title: Build the 'Institutional Wiki' in src/docs/knowledge-hub.js. This mod...

## Summary
- Repo orchestration task for via-decide/kup-research
- Goal: Build the 'Institutional Wiki' in src/docs/knowledge-hub.js. This module must automatically generate documentation from the 'Scenario 2' recovery logs. [span_16](start_span)[span_17](start_span)It should highlight "What Worked" and "Why It Failed" for extreme-climate AI[span_16](end_span)[span_17](end_span).

## Testing Checklist
- [ ] Run unit/integration tests
- [ ] Validate command flow
- [ ] Validate generated artifact files

## Risks
- Prompt quality depends on repository metadata completeness.
- GitHub API limits/token scope can block deep inspection.

## Rollback
- Revert branch and remove generated artifact files if workflow output is invalid.