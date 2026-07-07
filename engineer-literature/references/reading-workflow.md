# Reading Workflow

Use this reference for single-paper or small-cluster reading.

## Fast triage

Use when the user provides a title, abstract, DOI, arXiv link, or asks whether a paper
is worth reading.

Output:

- **一句话判断**: State the paper's engineering value in one sentence.
- **研究问题**: What problem or bottleneck the paper targets.
- **方法抓手**: The core model, algorithm, device, system, or experimental route.
- **证据强度**: What evidence is shown: benchmark, simulation, physical experiment,
  field test, ablation, theoretical proof, or case study.
- **适合引用的位置**: Introduction, related work, method motivation, benchmark choice,
  discussion, limitation, or future work.
- **是否值得精读**: yes/no/conditional, with the reason.

## Deep reading

Use for full PDFs, methods, experiments, or when the user is preparing a manuscript.

Read in this order:

1. Abstract and introduction: identify problem, claimed gap, and contribution.
2. Figures and captions: reconstruct the paper's argument visually.
3. Method section: extract assumptions, variables, model architecture, equations,
   pipeline, training/control/simulation settings, and implementation details.
4. Experiments: extract datasets, scenarios, baselines, metrics, ablations, uncertainty,
   and whether tests are simulation-only or physically validated.
5. Results and discussion: separate major findings from secondary observations.
6. Limitations: record explicit limitations and infer likely reviewer questions.

## Engineering extraction checklist

- System boundary: inputs, outputs, states, constraints, assumptions.
- Technical route: analytical model, numerical simulation, AI model, controller, sensor,
  hardware, optimization, or hybrid method.
- Evidence route: benchmark, ablation, sensitivity analysis, robustness, uncertainty,
  physical experiment, real-world deployment, or failure analysis.
- Reproducibility: code, data, hyperparameters, mesh/simulation settings, hardware,
  random seeds, evaluation protocol, and missing details.
- Writing value: cite for background, gap, method precedent, metric/baseline choice,
  limitation, or future direction.

## Chinese explanation style

Prefer clear Chinese paragraphs. Keep formulas and technical terms precise. If a method
is complex, explain it in three layers:

1. Intuitive idea.
2. Engineering implementation.
3. Mathematical or algorithmic detail.

