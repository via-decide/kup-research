# H0 — Repository/Contract Audit and Ownership Freeze

**Scope:** [KUP-RESEARCH-OS-001](https://github.com/via-decide/kup-research/issues/31), stage H0.
**Date:** 2026-09-03
**Method:** Every finding below is from direct inspection — `gh repo clone`, `git log`/`git show` on real merge diffs, `gh issue/pr list` against the live GitHub API, and reading actual file contents. Nothing here is inferred from repo names, READMEs alone, or prior chat summaries. Where a claim in the parent issue is repeated below, it has been independently re-verified, not just copied forward.

Repos audited: `kup-research`, `kup-program`, `LogicHub`, `electronics`, `Orchade`, `kup-network`, `kup-partnerships`, `kup-curriculum`, `GN8R` (the 9 named in H0), plus `kup-ai-systems-lab` and `kup-ai-stack` (named in PART F's ownership table and directly implicated by the parent issue's own flagged file).

---

## 1. The single most important finding: GN8R *is* "Simba," and it is the root cause of misleading merge history in six repos

`GN8R`'s own README describes a "Simba-style pipeline: audit → generate prompts → push branch → open PR." Its `src/templates.js` generates exactly four files per task — `codex-task.md`, `antigravity-repair-task.md`, `pr-package.md`, `execution.json` — under `artifacts/via-decide__{repo}/`.

Those exact four files, with that exact content shape, are what actually landed — repeatedly, as the *entire* diff — in dozens of merged PRs across `kup-network`, `kup-partnerships`, `kup-curriculum`, `kup-ai-systems-lab`, and `kup-ai-stack`, each PR titled as if it implemented a real feature. Confirmed directly on `kup-partnerships` PR #32 ("Build the 'Sovereign-Liquidity-Pool' in src/fin/pool-engine.js"): `git diff 52c8be0^1 52c8be0^2 --stat` shows 4 files changed, 7 insertions, 7 deletions, all under `artifacts/` — no `src/fin/pool-engine.js`, no `src/` directory at all in that repo, ever.

**Root cause, found in GN8R's own code, not just symptom:** `src/execution-pipeline.js`'s 11-stage pipeline (`FLIGHT_PLAN → PLAN → AUDIT → GENERATE → VALIDATE → ARTIFACTS → PUSH → PR → REVIEW → MERGE → COMPLETE`) only performs real code synthesis when a `createPath` parameter is supplied. When it isn't, PUSH and PR still run to completion using only the four template/meta files. Nothing in the pipeline blocks a PR from opening, or being merged, when zero real implementation exists. This is happening live, right now, in GN8R's own repo: **currently-open PR #25** wrote a file whose literal path is `1. gn8r/checks/file_pipeline_check.js 2. gn8r/integrations/ui_probe.js 3. extend gn8r/core/health.js` — the pipeline asked for a file path, got a numbered-list text reply instead, and wrote *that* to disk as a filename.

**Why this matters for every later H-stage:** the parent issue's negative tests (PART I) explicitly require "implementer self-review cannot satisfy an independent-review gate" and "a legacy unverified paper cannot be counted as an accepted publication." Simba-authored merges are a live, currently-operating instance of exactly the failure those tests are designed to catch — a bot audits its own output, generates a PR package describing success, and merges it, with no independent check that the described work exists. `kup-research` itself was not exempt: the flagged `papers/hfi_execution.md` and a second, previously-unflagged case (below) are both Simba output.

**Second `kup-research` case, found during this audit, not in the parent issue:** commit `2d36c7e` merges PR #29, titled "Generate dataset pipeline 'KUTCH-TIRE-ANOMALY' in datasets/generator.py." The merge diff touches only `artifacts/via-decide__kup-research/antigravity-repair-task.md` (2 lines). **No `datasets/` directory exists anywhere in `kup-research`, now or ever in its history.** The PR title, and by extension the merged-PR log, asserts a dataset pipeline was built. It was not.

**Action implied for H1+ (recorded here, not executed in H0):** GN8R's execution-pipeline should not run PUSH+PR when `createPath` (or equivalent real-deliverable evidence) is absent, and every Simba-merged PR across the six affected repos should be treated as **unverified until independently re-checked** — the merge having happened is not evidence the described work exists. This is a governance/tooling fix to GN8R itself, not a `kup-research` content problem to patch document-by-document.

---

## 2. Per-repository findings

### `kup-research` — verified: correct front door, currently near-empty, two Simba artifacts need labeling (H1)

Real repo. Current tree: `README.md` (14 bytes — literally `# kup-research`), `LICENSE`, `artifacts/via-decide__kup-research/*` (4 Simba template files), `papers/hfi_execution.md` (112 lines).

`papers/hfi_execution.md` is Simba output, and the audit trail proves it beyond the parent issue's own characterization: `artifacts/via-decide__kup-research/codex-task.md` contains the literal generation instruction — *"Document the April orchestration burst of 1100 contributions. Analyze the 18.8 activity/sec execution rate... Log 'RESEARCH_ARTIFACT: HFI_EXECUTION_PAPER_GENERATED'."* The paper was not a hallucination during analysis; it was written to order, with the numbers pre-specified in the prompt. The "1,100 contributions" and "18.8 activity/sec" have no source system, no citation, and reference generic "DC-East/DC-West/DC-Central" infrastructure that does not correspond to anything in this org.

Plus the KUTCH-TIRE-ANOMALY phantom merge from §1 above.

**Role per PART F ("public institution index, research programmes/projects/protocols/findings/publications"): confirmed correct, not yet built.** Nothing here contradicts the proposed role; there is simply almost nothing here yet. That is H1's job, not H0's.

### `kup-program` — real for KUP-STACK-001 only; task/runtime and publication contract are still open issues, not implementations

Directly re-verified this session (independent of chat history) against `origin/main` (`8ec7310`).

- **Real and tested:** `contracts/stack/v1/` — `KupCanonicalRef`, `KupInteropEnvelope`, `EngineeringArtifactExport` as Zod schemas with generated JSON Schema, a canonical-JSON `contentHash` standard, and a real `generate-consumer-types.ts` codegen pipeline. 57/57 tests passing as of this session's own work on PRs #63/#64. This is genuinely the "cross-system contracts" slice of PART F's proposed role.
- **Not yet real:** issue #55 (`KUP-RUNTIME-001`, "task/runtime") and #56 (`KUP-PUB-001`, "publication contract") are both **open, unimplemented issues** — confirmed via `gh issue list`, no PRs reference either. The pre-existing `core/measurement-engine.js`, `program/decision-engine.js`, `runtime/loop.js` etc. are a **disconnected experiment-loop scaffold that predates KUP-STACK-001** (already documented as such in this repo's own `docs/stack/SYSTEM_OWNERSHIP.md`, correction #1) — they are not an implementation of #55, despite the suggestive directory name `runtime/`.

**Role per PART F ("lifecycle, task/runtime, evidence acceptance, governance, cross-system contracts"): partially confirmed.** Cross-system contracts: yes, real. Task/runtime, evidence acceptance, governance: not yet built. H2 should map onto the real contracts (`contracts/stack/v1/`) and must not assume #55/#56 already provide runtime/governance machinery.

### `LogicHub` — real engineering contract layer, and the sensor calibration/evidence-grading claim is confirmed with a concrete, well-designed example

Confirmed real remote, active branches (`codex/kup-evidence-campaign-dashboard`, `codex/omni-wheel-evidence-campaign`, `codex/reframe-logichub-as-hardware-revision-control-2026-08-21` — real work in flight, worth checking before H3 starts). `engineering/packages/validation-engine/src/confidence.ts` defines a real, explicit evidence-confidence model:

```ts
CONFIDENCE_CLASSES = [
  'deterministic_verified_inputs', 'deterministic_estimated_inputs',
  'empirical_calibrated', 'heuristic', 'insufficient_evidence',
]
```

with `deriveConfidence()` correctly routing any missing/unknown-grade required input to `insufficient_evidence` rather than silently proceeding — i.e., a real, working instance of the `UNKNOWN != pass` principle PART B/PART I require, already built and in a package with its own tests.

**Role per PART F ("engineering state, apparatus/build/test/replication contracts and physical execution packets"): confirmed, with the caveat that PART B's ten candidate object names (`BuilderCapabilityManifest`, `BuildWorkOrder`, etc.) do not exist under those names anywhere in LogicHub today** — the `engineering/packages/contracts` package owns `Project`/`Revision`/`EngineeringObject`/`Constraint`/`Decision`/`Artifact`/`ChangeIntent`/`ValidationResult`/`Module`/`EngineeringPullRequest`, and `validation-engine` owns confidence/evidence grading, but nothing yet represents a physical build-work-order, a builder capability manifest, or a replication receipt. H3 is genuinely additive here, not duplicative — but should extend `validation-engine`'s confidence-class pattern rather than inventing a second evidence-grading scheme.

### `Orchade` — real, unrelated to H0's physical-work contracts, correctly scoped as field/property state

Re-verified `origin/main` (`c492d80`) this session. Property Model v1 (`EquipmentTwinDefinition`, `PropertyEquipmentInstance`) is real and tested (407/407 as of this session's own work). Nothing in Orchade currently represents apparatus/build/test/replication state — consistent with PART F's proposed role ("property/field state, observations, simulations, field-operational evidence") and with PART C2's engineering-replication-vs-field-replication split. No correction needed to this row.

### `electronics` — the strongest real precedent in the org for both the physical-work contracts AND the anti-fabrication governance PART A/B are trying to establish

By far the most substantial and real of the 9+2 repos: 48 commits (all real `feat/*`/`codex/*` merges — **not** the Simba pattern), ~1,049 tracked files, 43,527 lines. README claims match actual content: ESP32 firmware, a real NAND/FTL storage driver, a Python SSD simulator with unit/property/mutation/stateful tests, KiCad hardware design, and 10 fully worked example projects.

**This repo already has informal, working analogues to four of PART B's ten candidate contracts, under different names:**

| PART B candidate | Existing `electronics` analogue |
|---|---|
| `TestRunReceipt` (+ partial `InstrumentRef`) | `assets/evidence/evidence.schema.json` — required fields include `fixture_id`, `board_revision`, `firmware_commit`, `nand_profile_sha256`, `instrument`, `raw_artifact_path`, `sha256`, `procedure`, `measured_values`, `limits`, `result` (`PASS`/`FAIL`), `human_reviewer`, and a `classification` enum of `REAL_MEASUREMENT`/`SYNTHETIC_EXAMPLE` |
| `ApparatusRevision` | `hardware/platforms/w25n01jw_lab/platform.yaml` — a real status lifecycle: `DESIGN_DRAFT → DESIGN_RULES_PASSED → ASSEMBLED_UNVERIFIED → BENCH_PARTIAL → BENCH_VERIFIED → REJECTED`, plus `board_revision`, `required_evidence` |
| `MaterialLotRef` (partial) | `hardware/platforms/sovereign_cartridge_proto0/bom/bom.csv` — `freeze_status` (`FROZEN`/`BLOCKED`/`DEFERRED`), `procurement_gate` (e.g. `AUTHORIZED_SOURCE_AND_LOT_TRACE_REQUIRED`) |
| (versioning convention) | `topology.json`/`spi-ownership.json`/`usb-service.json`/`power-safety.json` all carry a `"revision": "PROTO-0"` field |

None of these are named/shared cross-repo contract types — each is a repo-local convention — but H3 should treat this as **the closest thing to prior art the org has**, and reconcile against it explicitly rather than starting PART B's ten objects from a blank page.

**Governance precedent, directly relevant to PART A/G:** `docs/authoritative-research-policy.md` already states *"Do not invent timing, current, voltage, impedance, memory, endurance, or throughput values,"* with a four-tier claim classification (established practice / vendor recommendation / implementation decision / future proposal). `docs/research/electronics-from-zero-repository-audit.md` is a real, dated self-audit that explicitly lists what remains `UNKNOWN` rather than claiming completion. This is exactly the discipline PART G asks `kup-research` to adopt — it is already proven out here.

**One real weak spot, worth flagging on the same "don't let mocked-as-real slip through" grounds as this org's other audits this session:** `backend/cloud/providers/configured_provider.py`, in its entirety, is:
```python
from .mock import MockProvider
class ConfiguredProvider(MockProvider):
    name = "configured"
```
The provider meant to represent a real, configured cloud connection is a bare `MockProvider` subclass with no override; `mock.py`'s `submit()` returns a canned `{"state": "CANDIDATE", ...}` regardless of input. A grep of all of `backend/` (259 lines) for real network calls (`requests.`, `boto3`, `google.cloud`, `fetch(`) found none. This does not affect the firmware/hardware side, which is real, but the "hybrid cloud job" feature described in `docs/operations/hybrid-deployment.md` is not backed by a real cloud path today.

### `kup-network`, `kup-partnerships`, `kup-curriculum` — confirmed empty scaffolds, entirely Simba-pattern history, zero real code

All three: `README.md` (1-line stub), `LICENSE`, `artifacts/via-decide__{repo}/*` only. No `src/` directory in any of the three, despite (respectively) 1, 33, and 16 merged PRs whose titles claim specific implementations (e.g. `kup-partnerships` PR titles reference `src/fin/pool-engine.js`, `src/api/fl...`, `src/bridge/...`, `src/web/inf...`, `src/data/...`, `src/integrat...` — none exist). Zero open issues, zero open PRs on all three.

**Latent risk found in all three, not yet materialized:** `kup-ai-systems-lab/KUP_CLAUDE_CODE_EXECUTION_PROMPTS.md` contains prewritten "PROMPT" blocks specifically targeting `kup-partnerships` (fabricated figures: *"5 strategic partnerships by Month 6," "NHAI: 'Real-time tire health monitoring → 2% fuel cost reduction'," "₹1Cr capital → ₹100L Year 1 revenue → ₹500L+ Year 3"*) and `kup-curriculum` (*"37 tools, 500K MAU," "Pipeline accuracy >80%," "30 co-founders"*). None of the files these prompts would generate exist yet in either repo. This is a seed, not a fact — but it means both repos are one careless prompt-execution away from acquiring the same kind of fabricated content already found in `kup-research`.

**Role per PART F: confirmed correct as future-only roles, correctly still un-built.** PART F already says "currently do not invent runtime" / "not a technical evidence authority" for these three — the audit confirms that instruction matches reality; there is nothing to un-repurpose.

### `kup-ai-systems-lab` — hosts the flagged prompt file, plus two real-but-disconnected simulation files

172 commits, 35 merged PRs, overwhelmingly Simba-pattern, with two real exceptions: `src/infra/event-buffer.cpp` (91 lines, a lock-free ring buffer — no build system references it anywhere in the repo, unintegrated) and `src/simulation/traffic-predictor.py` (134 lines, a real rolling-Markov predictor, but its own `__main__` block runs against 3 hardcoded synthetic sensor readings, not a live feed).

Beyond the numbers the parent issue already quoted, `KUP_CLAUDE_CODE_EXECUTION_PROMPTS.md` (649 lines) contains further fabricated-as-fact framing worth recording: *"Problem statement: '95% GenAI projects fail in extreme climate environments'"* (no citation), *"Target: 1K+ citations by Month 18 (calculated backward from venue impact factors)"* (explicitly instructs backward-deriving a citation count from a target, inverted from how a real citation count would be produced), *"500K MAU on www.viadecide.com by Month 12."* This file is the seed template for the latent risk noted in `kup-partnerships`/`kup-curriculum` above, plus `kup-research`, `kup-program`, and `kup-ai-stack` — six repos in total are named as prompt targets in this one file.

### `kup-ai-stack` — mostly Simba, but three real, non-trivial (still disconnected) implementations

246 commits, 50 merged PRs, mostly Simba-pattern, with real exceptions: `src/orchestrator/global-executor.js` (SHA-256 majority-consensus reconciliation across 100 simulated in-process nodes — not real distributed nodes), `src/engine/sensor-handler-v2.js` (a real 1D Kalman filter + hysteresis state machine + Gay-Lussac pressure/temperature physics, cleanly written), and `test-scenario2.sh`/`deploy.sh`.

**Worth flagging directly:** `sensor-handler-v2.js`'s header comment states *"Accuracy target: >92% at 48°C ambient"* and *"CompactPayload: 68 bytes fixed — 90% token savings vs legacy JSON blob"* as if these were validated results. They are real *outputs of `test-scenario2.sh` running against `Math.random()`-generated synthetic packets*, not field measurements. `deploy.sh` brands itself "KUP SOVEREIGN DEPLOY" but only clones a local repo and runs local smoke tests — no cloud call, device flash, SSH, or external endpoint anywhere in it, despite the name.

### `GN8R` — see §1. Real, live, actively developed — and the direct source of the org-wide misleading-PR pattern

24 merge commits, 7,314 lines, genuinely real GitHub/Gitea/Telegram API integration (`fetch` against real hosts) and a real local-only AI backend (Ollama at `localhost:11434` + an optional local RAG server — README states plainly *"No external API. No cloud. No fallback,"* meaning the AI-generation feature only works when an operator is running that stack locally, not as a hosted service).

Two open PRs on GN8R's own repo right now: **#25**, exhibiting the malformed-path bug live (see §1), whose artifact files were also written to `artifacts/via-decide__gn8r/` — lowercase — while the real repo is `GN8R`, a casing bug in the path-generation logic; and **#12**, an 18,401-line addition of unrelated static biography pages (`people/ada-lovelace/index.html`, etc.) that has nothing to do with KUP or bot functionality and appears to be misfiled/unrelated content sharing this repo.

**Role per PART F ("software execution worker / future lab runner"): confirmed as a real, working direction, but not yet safe to point at physical-work orchestration (H3+) without first fixing the PUSH+PR-without-real-deliverable behavior documented in §1.**

---

## 3. Ownership map — PART F's table, verified against real code

| Repository | PART F's proposed role | Audit verdict |
|---|---|---|
| `kup-research` | public institution index | **Confirmed, correct, currently ~empty.** No conflicting content beyond the two Simba artifacts (§2), which need labeling under PART G in H1, not deletion. |
| `kup-program` | lifecycle/runtime/evidence/governance/cross-system contracts | **Confirmed for cross-system contracts only.** Runtime/evidence/governance are open issues (#55/#56), not implementations — H2 must not assume they exist yet. |
| `LogicHub` | engineering/apparatus/build/test/replication contracts | **Confirmed.** Real evidence-confidence model already exists (`validation-engine`); the ten PART B object names do not exist yet — genuinely additive work for H3. |
| `electronics` | reusable instrumentation/fixtures | **Confirmed and understated** — this repo already has the org's strongest informal precedent for both the physical-work contracts (§2 table) and the anti-fabrication governance model (§2 quote). Recommend H3 explicitly reconciles against it. |
| `Orchade` | property/field state | **Confirmed, no correction needed.** |
| `kup-network` | future node directory, no runtime yet | **Confirmed correct as-is** — genuinely empty, matches "do not invent runtime" instruction already in the issue. |
| `kup-partnerships` | future partnership workflow, not evidence authority | **Confirmed correct as-is**, plus a latent fabricated-content risk from `KUP_CLAUDE_CODE_EXECUTION_PROMPTS.md` recorded in §2 for whoever picks up H7. |
| `kup-curriculum` | future learning pathways, not evidence authority | **Confirmed correct as-is**, same latent risk noted. |
| `kup-ai-systems-lab` | legacy/specialized AI assets after audit | **Confirmed** — now audited; two disconnected-but-real files identified, one 649-line prompt file confirmed as the org-wide fabrication-risk source. |
| `kup-ai-stack` | legacy/specialized AI assets after audit | **Confirmed** — now audited; three disconnected-but-real files identified. |
| `GN8R` | software execution worker / future lab runner | **Confirmed as a real direction, with a concrete, currently-live bug (§1) that should be fixed before this repo is trusted for H3+ physical-work orchestration.** |

No row in PART F's table was contradicted by live code. The table can be frozen as-is; the corrections above are about *current build status*, not role assignment.

---

## 4. Explicit gaps and unknowns (required by H0)

- **Unknown:** whether any of the Simba-merged PRs across `kup-network`/`kup-partnerships`/`kup-curriculum`/`kup-ai-systems-lab`/`kup-ai-stack` were reviewed by a human before merge, or auto-merged. GN8R's `execution-pipeline.js` has an auto-merge stage gated by env flags (`SIMBA_ALLOW_LIVE_PUSH`/`SIMBA_ALLOW_LIVE_PR`) whose actual configured values were not inspected in this audit (would require access to GN8R's live deployment environment, not just its source).
- **Unknown:** total count of Simba-pattern PRs org-wide beyond the 5 repos audited here — this H0 pass covered the 9 repos the parent issue named plus 2 more from PART F's table; it did not search every `via-decide` repository for the same pattern.
- **Gap:** no repo in this audit currently implements any of PART B's ten candidate contract names. `electronics` has the closest informal analogues (§2); nothing else does.
- **Gap:** LogicHub's active branches (`codex/kup-evidence-campaign-dashboard`, `codex/omni-wheel-evidence-campaign`, `codex/reframe-logichub-as-hardware-revision-control-2026-08-21`) were identified as existing but not inspected in depth in this pass — H2/H3 should check whether any of that in-flight work already overlaps PART B's candidate objects before adding new ones.
- **Unknown:** whether `kup-program`'s `runtime/loop.js` scaffold (predates KUP-STACK-001, confirmed unrelated to it) has any salvageable logic for #55's eventual task/runtime implementation, or whether it should be treated as fully legacy. Not assessed in this pass.

---

## 5. What this means for H1 onward

1. **H1** (`kup-research` front door): archive/label `papers/hfi_execution.md` under PART G's `archive/legacy-unverified` convention, and add an equivalent note for the KUTCH-TIRE-ANOMALY phantom-merge finding (§1) — the merged-PR log itself is misleading and should carry a correction, not just the paper.
2. **H2** (research ↔ KUP lifecycle mapping): map onto `kup-program`'s real `contracts/stack/v1/` only; treat #55/#56 as not-yet-available.
3. **H3** (LogicHub physical-work contracts): reconcile against `electronics`'s existing `evidence.schema.json`/`platform.yaml`/`bom.csv` conventions (§2 table) and extend `validation-engine`'s confidence-class model, rather than starting from zero.
4. **Before H3-H7 involve GN8R as an execution worker:** fix the PUSH+PR-without-real-deliverable behavior in `execution-pipeline.js` (§1). Until then, GN8R merging its own PRs should not be treated as evidence that described work exists — for GN8R's own repo or any other.
