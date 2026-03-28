You are working in repository via-decide/kup-research on branch main.

MISSION
Launch KUTCH-TIRE-ANOMALY (KTA) Dataset project. Create dataset schema: vehicle_id, passage_timestamp, vehicle_type, speed, axle_force_left, axle_force_right, temperature_ambient, tire_pressure_label, tire_condition_label, road_surface, weather_condition. Generate 1M vehicle passages from digital twin: 800K normal, 150K under-inflated, 30K critical pressure, 20K damaged. Create official documentation: README.md (dataset overview), DATASHEET.md (use cases, limitations, ethical considerations), CITATION.cff (how to cite). Host on Hugging Face Datasets: https://huggingface.co/datasets/via-decide/kutch-tire-anomaly Create benchmark tasks: (a) binary classification (normal vs. anomaly), (b) 4-way classification (normal/low/critical/damaged), (c) tire pressure regression. Provide baseline models: Random Forest, LSTM-Autoencoder, Isolation Forest. Create leaderboard on Weights & Biases tracking: accuracy, precision, recall, F1, inference latency on edge hardware. Draft "Dataset Paper" for ICML/NeurIPS: motivate the problem, describe data collection, share baseline results, discuss limitations.

CONSTRAINTS
Must be citable (DOI registration). Must include privacy considerations (synthetic data only, no real vehicle IDs). Leaderboard must encourage edge inference focus (not just accuracy, but accuracy/latency tradeoff).

PROCESS (MANDATORY)
1. Read README.md and AGENTS.md before editing.
2. Audit architecture before coding. Summarize current behavior.
3. Preserve unrelated working code. Prefer additive modular changes.
4. Implement the smallest safe change set for the stated goal.
5. Run validation commands and fix discovered issues.
6. Self-review for regressions, missing env wiring, and docs drift.
7. Return complete final file contents for every modified or created file.

REPO AUDIT CONTEXT
- Description: 
- Primary language: unknown
- README snippet:
# kup-research

- AGENTS snippet:
not found


SOP: PRE-MODIFICATION PROTOCOL (MANDATORY)
1. Adherence to Instructions: No deviations without explicit user approval.
2. Mandatory Clarification: Immediately ask if instructions are ambiguous or incomplete.
3. Proposal First: Always propose optimizations or fixes before implementing them.
4. Scope Discipline: Do not add unrequested features or modify unrelated code.
5. Vulnerability Check: Immediately flag and explain security risks.

OUTPUT REQUIREMENTS
- Include: implementation summary, checks run, risks, rollback notes.
- Generate branch + PR package.
- Keep prompts deterministic and preservation-first.