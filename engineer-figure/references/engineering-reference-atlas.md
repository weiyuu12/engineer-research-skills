# Engineering Reference Atlas

Use this reference before designing figures for engineering, deep learning, modeling,
simulation, control, robotics, digital twins, neural operators, reinforcement learning,
inverse design, trajectory evidence, or interception-style systems.

The source images live in `../assets/engineering-reference-atlas/`. Treat them as
visual references for structure, hierarchy, and scientific storytelling. Do not copy
their content into a user's manuscript figure. If a source figure itself will be reused,
verify the article license and cite the source.

## Replacement policy

For engineering and AI-control tasks, this atlas replaces the older bio/chemistry-heavy
gallery as the first visual inspiration source.

- Use this atlas to choose the figure's **visual argument**.
- Use `demos.md`, `common-patterns.md`, and `api.md` for reusable Python code patterns.
- Use `typography-layout-contract.md` for Chinese fonts, readable size ladders, margins,
  and anti-overlap rules.
- Use the older chart atlas only after deciding that metric comparison is truly the
  main job of the figure.

## How to use it

1. Identify the figure's main job: architecture, training process, simulation evidence,
   control loop, inverse design, robotics testbed, or feedback mechanism.
2. Pick one or two closest references below.
3. Extract the layout idea, not the paper-specific content: hero panel position,
   evidence rows, flow direction, callout style, validation insets, and legend strategy.
4. Convert the user's data into that structure with the selected Python or R backend.
5. Run the visual quality loop and typography/layout contract before final delivery.

## Fast routing

| User's figure job | Start with | Why |
|---|---|---|
| Deep learning framework or unified model | `01`, `02`, `03` | Architecture/training/search story instead of isolated metrics |
| Digital twin, neural operator, PINN, surrogate simulation | `04`, `05`, `06`, `19`, `21`, `23` | Shows physical state, learned mapping, and validation evidence together |
| Reinforcement learning or control loop | `07`, `08`, `09`, `10`, `11`, `24` | Makes observation-policy-action-feedback visible |
| Engineering inverse design or system optimization | `12`, `13`, `15`, `22` | Connects design space, learned predictor, physical system, and verification |
| Robotics, embodied AI, real-world testbed | `16`, `17`, `25` | Combines task scene, perception/planning, and execution/validation |
| Data feedback, degradation, mechanism risk | `18` | Makes recursive process and failure mechanism visible |

## Reference list

| ID | Local asset | Visual lesson | Best used for |
|---|---|---|---|
| 01 | `01_model_architecture_training/01_emu3_next_token_multimodal_model_Nature2025_Fig1.png` | Unified model architecture with inputs, representation, and task outputs | Multimodal or multi-input model framework |
| 02 | `01_model_architecture_training/02_deepseek_r1_rl_reasoning_training_Nature2025_Fig1.png` | Training stages plus reinforcement-learning signal and capability evolution | Training pipeline, post-training, RL-for-reasoning |
| 03 | `01_model_architecture_training/03_rl_algorithm_discovery_Nature2025_Fig1.png` | Search space, candidate discovery, selection, and validation as one story | Algorithm discovery, AutoML, RL algorithm generation |
| 04 | `02_simulation_surrogate_physics/04_myoelectric_digital_twin_NatCommun2023_Fig1.png` | Simulation-generated data to AI training to real-system use | Digital twin, synthetic data, sim-to-real |
| 05 | `02_simulation_surrogate_physics/05_deep_neural_operator_free_boundary_NMI2026_Fig1.png` | Mathematical object, neural mapping, and physical prediction domain | Neural operator or PDE surrogate overview |
| 06 | `02_simulation_surrogate_physics/06_deep_neural_operator_free_boundary_NMI2026_Fig2.png` | Physical fields, predicted-vs-true comparison, and error evidence | Simulation validation, field prediction, error panels |
| 07 | `03_control_reinforcement_learning/07_robot_lifelong_rl_NMI2025_Fig1.png` | Robot task stream plus knowledge preservation/combination mechanism | Lifelong learning, transfer, robot RL |
| 08 | `03_control_reinforcement_learning/08_network_control_model_based_rl_NMI2024_Fig1.png` | Large-scale system, decentralized control, communication, and scalability | Multi-agent control, network control, distributed RL |
| 09 | `03_control_reinforcement_learning/09_sindy_rl_interpretable_control_NatCommun2025_Fig1.png` | Dynamics, reward, and policy decomposed into interpretable modules | Model-based RL, interpretable control, mechanism panels |
| 10 | `03_control_reinforcement_learning/10_sindy_rl_control_tasks_NatCommun2025_Fig2.png` | Control-task schematic paired with outcome evidence | Benchmark tasks, trajectories, state-response evidence |
| 11 | `03_control_reinforcement_learning/11_microrobot_model_based_rl_NMI2025_Fig1.png` | Perception, imagined environment, action, and feedback in a closed loop | Model-based RL, navigation, autonomous control |
| 12 | `04_engineering_design_systems/12_rf_inverse_design_emulator_NatCommun2024_Fig1.png` | Design library, inverse target, learned EM predictor, and fabricated examples | Inverse design, surrogate modeling, engineering optimization |
| 13 | `04_engineering_design_systems/13_rf_inverse_design_validation_NatCommun2024_Fig2.png` | Learned predictor vs physical simulation/manufacturing validation | Model validation, parametric engineering design |
| 15 | `04_engineering_design_systems/15_plasma_dynamics_trajectory_evidence_NatCommun2025_Fig2.png` | Trajectory response evidence and control-relevant temporal comparison | Robust trajectory, system response, predict-first experiments |
| 16 | `05_robotics_embodied_ai/16_embodied_llm_robot_framework_NMI2025_Fig1.png` | Task planning, perception, retrieval, and robot execution architecture | LLM + robotics, embodied planning, sensor feedback |
| 17 | `05_robotics_embodied_ai/17_causal_chambers_physical_testbed_NMI2024_Fig1.png` | Physical testbed, variable manipulation, and algorithm validation | Experimental platforms, causal testing, sim-to-real validation |
| 18 | `06_mechanism_data_feedback/18_model_collapse_feedback_loop_Nature2024_Fig1.png` | Recursive process plus failure/degradation mechanism | Data feedback loops, model degradation, risk mechanism |
| 19 | `02_simulation_surrogate_physics/19_latent_neural_operator_complex_dynamics_NatCommun2024_Fig1.png` | Latent representation plus nonlinear operator prediction | Complex dynamics, low-dimensional surrogate, real-time prediction |
| 21 | `02_simulation_surrogate_physics/21_physics_informed_gnn_dynamics_NatCommun2026_Fig1.png` | Conservation laws embedded into graph message passing | Physics-informed GNN, dynamics, invariant/equivariant modeling |
| 22 | `04_engineering_design_systems/22_battery_pinn_soh_NatCommun2024_Fig1.png` | Mechanistic prior plus data model plus prognosis task | Battery/energy systems, state estimation, degradation prediction |
| 23 | `02_simulation_surrogate_physics/23_interpretable_network_dynamics_symbolic_NatCommun2025_Fig1.png` | Black-box observations to interpretable governing equations | Symbolic regression, interpretable dynamics, equation discovery |
| 24 | `03_control_reinforcement_learning/24_model_free_tracking_control_NatCommun2023_Fig1.png` | Training/testing controller schematic paired with target trajectory evidence | Tracking control, desired trajectories, model-free control |
| 25 | `05_robotics_embodied_ai/25_dronehub_robotics_testbed_npjRobotics2025_Fig7.png` | Physical robotics platforms plus ROS, localization, environmental sensing, video, and feedback data streams | Robotics testbeds, sensor systems, experimental platforms |

## Visual moves to borrow

- Make the method/process the hero when the claim is methodological.
- Put final metrics in smaller validation panels, not automatically in panel `a`.
- Use arrows only for real information, material, state, or decision flow.
- Keep physical/simulation snapshots close to the model stage that produced them.
- Pair abstract modules with one concrete example so the figure does not become a
  generic flowchart.
- Use one color family for the proposed method, one neutral family for baselines, and
  one restrained accent for control signals, errors, thresholds, or risk.
- Prefer evidence thumbnails, trajectory snippets, field maps, or state diagrams over
  another large bar chart when mechanism or process is the real point.

## Source and license notes

The image URLs and article URLs are recorded in
`../assets/engineering-reference-atlas/manifest.csv`. Most entries were selected from
open-access Nature, Nature Machine Intelligence, and Nature Communications pages. Some
articles mention Creative Commons without an automatically parsed exact license string;
verify the article page before redistributing a source image outside this skill.
