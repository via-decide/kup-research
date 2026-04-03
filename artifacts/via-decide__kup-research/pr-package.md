Branch: simba/implement-the-hugging-face-uploader-in-srcpublis
Title: Implement the 'Hugging Face Uploader' in src/publish/hf-hub-sync.js. ...

## Summary
- Repo orchestration task for via-decide/kup-research
- Goal: Implement the 'Hugging Face Uploader' in src/publish/hf-hub-sync.js. This module must interface with the Hugging Face API to upload the Parquet-formatted KUTCH-TIRE-ANOMALY dataset.

## Testing Checklist
- [ ] Run unit/integration tests
- [ ] Validate command flow
- [ ] Validate generated artifact files

## Risks
- Prompt quality depends on repository metadata completeness.
- GitHub API limits/token scope can block deep inspection.

## Rollback
- Revert branch and remove generated artifact files if workflow output is invalid.