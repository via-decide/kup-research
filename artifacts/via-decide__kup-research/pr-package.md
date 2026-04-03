Branch: simba/build-the-impact-scraper-in-srcanalyticscitation
Title: Build the 'Impact Scraper' in src/analytics/citation-tracker.py. Crea...

## Summary
- Repo orchestration task for via-decide/kup-research
- Goal: Build the 'Impact Scraper' in src/analytics/citation-tracker.py. Create a service that monitors Hugging Face downloads and Google Scholar citations for your published papers and datasets.

## Testing Checklist
- [ ] Run unit/integration tests
- [ ] Validate command flow
- [ ] Validate generated artifact files

## Risks
- Prompt quality depends on repository metadata completeness.
- GitHub API limits/token scope can block deep inspection.

## Rollback
- Revert branch and remove generated artifact files if workflow output is invalid.