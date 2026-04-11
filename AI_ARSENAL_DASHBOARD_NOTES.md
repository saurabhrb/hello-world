# AI Arsenal Dashboard Recommendations

## Product framing
- Keep the metaphor consistent:
  - **Scenario** = Soldier.
  - **Plugin bundle** = Weapon class (Gun, Rocket Launcher, Grenade).
  - **Skill composition** = Gun attachments.
  - **MCP servers + CLI tools** = Internal parts.
  - **Per-tool operations** = Sub-parts.

## Suggested metric system
Use six top-line metrics for both game and AI views:
- Attack (task completion power)
- Reliability (consistency / failure rate inverse)
- Coverage (breadth of tasks handled)
- Latency (inverse normalized speed)
- Cost Efficiency (quality per token/compute)
- Robustness (resistance to edge cases/adversarial prompts)

## Cascading interaction model
1. Compute local deltas at each layer from ablation tests.
2. Apply peer-level coupling matrix (same-level side effects).
3. Roll impact to parent node using weighted aggregation.
4. Recompute globally with scenario stress factor.

This gives the behavior you described: changing one tool can force compensation in sibling tools and propagate upward.

## Two-view UX guidance
### 1) Regular user (gunsmith view)
- Simple attachment swaps and immediate score deltas.
- “Before vs After” bars and a single confidence indicator.
- Narrative recommendation (“Good for coding tasks, risky for legal QA”).

### 2) Advanced user (science view)
- Layered ablation table.
- Distribution chart for each metric (mean, P95, failure tails).
- Pairwise interaction heatmap (which tool replacements create collateral damage).
- Drift timeline across builds/version updates.

## Data collection recommendations
- Store raw run-level logs per scenario version.
- Keep seed, prompt set, dataset split, and infra profile to ensure reproducibility.
- Run both single-component ablation and pairwise ablation for strong interactions.
- Record forced substitution paths (which tool picked up slack when one was removed).

## Decision support features
- “Safe-to-ship” threshold with explainable blockers.
- Dependency graph alerts when updating one MCP/tool can destabilize others.
- Suggested mitigation plan: e.g., “if Tool X removed, enable helper script Y and adjust routing policy.”
