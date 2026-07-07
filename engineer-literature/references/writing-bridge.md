# Writing Bridge

Use this reference when literature needs to become Chinese thesis/manuscript material.

## Convert reading into writing

Map each paper into one of these writing roles:

- **背景趋势**: shows why the field matters or is moving in a direction.
- **问题缺口**: proves an unresolved limitation, bottleneck, or practical constraint.
- **方法依据**: justifies a modeling, simulation, control, optimization, or AI route.
- **对比对象**: supplies baselines, metrics, datasets, or experimental protocols.
- **结果参照**: gives typical performance ranges, failure modes, or validation standards.
- **讨论支撑**: supports limitations, robustness, generalization, or future work.

## Chinese writing outputs

For introduction:

- Field importance.
- Technical bottleneck.
- Existing routes and their limits.
- The specific gap this manuscript addresses.
- The user's proposed contribution.

For related work:

- Organize by method families, not by a list of papers.
- Compare assumptions, data/system setting, evidence level, and limitations.
- End each paragraph with the remaining gap.

For discussion:

- Explain what the results mean relative to prior work.
- State when the method works, when it may fail, and what evidence is still missing.
- Avoid overstating novelty from one comparison.

## Phrase patterns

Use these as patterns, not fixed text:

- "已有研究主要从 A、B 和 C 三条路线展开，其中 A 强调..., B 侧重..., C 则试图..."
- "然而，在工程应用场景中，仍存在...这一限制，尤其体现在..."
- "与侧重于...的方法不同，本文更关注..."
- "该类方法为本文的...提供了直接参考，但其...假设限制了在...场景下的适用性。"
- "因此，仍有必要构建一种能够同时兼顾...与...的技术路线。"

## Figure and experiment reuse

When a paper's figures are useful, extract the visual logic rather than copying content:

- method pipeline;
- system/control loop;
- simulation-to-real evidence chain;
- ablation or robustness layout;
- failure-case analysis;
- benchmark comparison table.

Route actual figure creation to `engineer-figure` when the user asks to draw or redesign
figures from the literature insight.

