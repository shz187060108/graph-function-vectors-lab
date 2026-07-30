# GenesisGFM M3 rebuild status — 2026-07-30

## Scientific state

**M3 remains NOT PASSED.**

The exact one-seed development smoke protocol now passes all of its frozen gates, but the milestone cannot be promoted until the formal three-seed run passes independently for Spring and Charge, IID and OOD, including active intervention and all causal graph interventions.

## One-seed frozen smoke result

| System | Split | Graph AUROC | Future MSE | Delete degradation | Wrong-sign degradation |
|---|---:|---:|---:|---:|---:|
| Spring | IID | 0.9986 | 0.000093 | +280.42x | +790.84x |
| Spring | OOD | 0.9543 | 0.007655 | +12.60x | +37.24x |
| Charge | IID | 0.9775 | 0.000160 | +274.42x | +828.74x |
| Charge | OOD | 0.9485 | 0.001395 | +133.88x | +395.19x |

Active information-gain improvement over random intervention:

- Spring: +0.0518 AUROC
- Charge: +0.0324 AUROC

## Structural changes

- Typed, signed, executable operator graph.
- No cross-object decoder bypass outside graph-gated messages.
- Explicit pre-intervention observation frame.
- Joint posterior over multiple intervention views.
- Evidence-normalized support confidence: `|c_ij| / SE(c_ij)`.
- Global graph information-gain intervention selection.
- Fault-tolerant sharded formal protocol: calibration shards, immutable registry freeze, evaluation shards, aggregation.

## Remaining blockers

1. Run the formal configuration for seeds 1, 2, and 3.
2. Preserve separate per-seed baseline registries and paired confidence intervals.
3. Audit the known-operator-family assumption. The current constructor is given the Spring or Charge kernel family; this establishes zero-edge-label identifiability and causal execution, but not yet the broader cross-operator GenesisGFM claim.
4. Compare this analytical system-identification constructor as a strong unsupervised baseline against a learned amortized relation-construction operator.

No one-seed or averaged result may override a failed formal setting.