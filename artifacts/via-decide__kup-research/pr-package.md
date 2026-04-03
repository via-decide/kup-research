Branch: simba/create-the-impact-story-generator-in-srcpublishf
Title: Create the 'Impact-Story' generator in src/publish/founder-story.js. ...

## Summary
- Repo orchestration task for via-decide/kup-research
- Goal: Create the 'Impact-Story' generator in src/publish/founder-story.js. This module uses the 'Academic Publisher' agent to draft a 500-word "Mission Brief" for each project.

## Testing Checklist
- [ ] Run unit/integration tests
- [ ] Validate command flow
- [ ] Validate generated artifact files

## Risks
- Prompt quality depends on repository metadata completeness.
- GitHub API limits/token scope can block deep inspection.

## Rollback
- Revert branch and remove generated artifact files if workflow output is invalid.