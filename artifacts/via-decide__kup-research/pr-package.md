Branch: simba/create-the-strategy-ingester-in-srcbridgeviadeci
Title: Create the 'Strategy Ingester' in src/bridge/viadecide-link.js. This ...

## Summary
- Repo orchestration task for via-decide/kup-research
- Goal: Create the 'Strategy Ingester' in src/bridge/viadecide-link.js. This module must pull real-time drift detection and blowout-risk data from the lab and format it into "Strategic Insight Reports" for ViaDecide. [cite_start]constraints: The output must include ONDC-compatible metadata to trigger commercial discovery for tire inventory or maintenance services.[span_7](end_span)[span_8](end_span)[span_9](end_span)

## Testing Checklist
- [ ] Run unit/integration tests
- [ ] Validate command flow
- [ ] Validate generated artifact files

## Risks
- Prompt quality depends on repository metadata completeness.
- GitHub API limits/token scope can block deep inspection.

## Rollback
- Revert branch and remove generated artifact files if workflow output is invalid.