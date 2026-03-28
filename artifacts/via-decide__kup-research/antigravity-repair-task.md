Repair mode for repository via-decide/kup-research.

TARGET
Validate and repair only the files touched by the previous implementation.

TASK
Launch KUTCH-TIRE-ANOMALY (KTA) Dataset project. Create dataset schema: vehicle_id, passage_timestamp, vehicle_type, speed, axle_force_left, axle_force_right, temperature_ambient, tire_pressure_label, tire_condition_label, road_surface, weather_condition. Generate 1M vehicle passages from digital twin: 800K normal, 150K under-inflated, 30K critical pressure, 20K damaged. Create official documentation: README.md (dataset overview), DATASHEET.md (use cases, limitations, ethical considerations), CITATION.cff (how to cite). Host on Hugging Face Datasets: https://huggingface.co/datasets/via-decide/kutch-tire-anomaly Create benchmark tasks: (a) binary classification (normal vs. anomaly), (b) 4-way classification (normal/low/critical/damaged), (c) tire pressure regression. Provide baseline models: Random Forest, LSTM-Autoencoder, Isolation Forest. Create leaderboard on Weights & Biases tracking: accuracy, precision, recall, F1, inference latency on edge hardware. Draft "Dataset Paper" for ICML/NeurIPS: motivate the problem, describe data collection, share baseline results, discuss limitations.

RULES
1. Audit touched files first and identify regressions.
2. Preserve architecture and naming conventions.
3. Make minimal repairs only; do not expand scope.
4. Re-run checks and provide concise root-cause notes.
5. Return complete contents for changed files only.

SOP: REPAIR PROTOCOL (MANDATORY)
1. Strict Fix Only: Do not use repair mode to expand scope or add features.
2. Regression Check: Audit why previous attempt failed before proposing a fix.
3. Minimal Footprint: Only return contents for the actual repaired files.

REPO CONTEXT
- README snippet:
# kup-research
- AGENTS snippet:
not found
- package.json snippet:
not found