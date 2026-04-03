Branch: simba/build-the-academic-formatter-in-srcpublishlatex-
Title: Build the 'Academic Formatter' in src/publish/latex-gen.js. Automatic...

## Summary
- Repo orchestration task for via-decide/kup-research
- Goal: Build the 'Academic Formatter' in src/publish/latex-gen.js. Automatically generate a LaTeX table comparing the F1-scores of 'Vanilla Week 1' models vs. 'Sovereign Week 3' (Kalman + Thermal) models across the 1M passage dataset.

## Testing Checklist
- [ ] Run unit/integration tests
- [ ] Validate command flow
- [ ] Validate generated artifact files

## Risks
- Prompt quality depends on repository metadata completeness.
- GitHub API limits/token scope can block deep inspection.

## Rollback
- Revert branch and remove generated artifact files if workflow output is invalid.