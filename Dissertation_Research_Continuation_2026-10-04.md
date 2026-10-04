# Research continuation — 2026-10-04

## Authoritative state

Use the October 4 checkpoint HANDOFF.md and dissertation version 16 over the repository root October 2 handoff. Subsequent chat-provided Chapter 7 replacements remain pending source verification. No repository push was performed.

## Completed saved-data verification in this session

Re-executed reproduce_audit.py from CH05_Fixed_Model_Performance_Negative_Control_Audit_v1.zip, with all assertions passing.

- Baseline ROC-AUC: 0.4164 on 100 unique ISIC images, 50 per class. Repeated probabilities and labels agree across attribution methods.
- Negative controls: 3,600 unique tasks across random-uniform maps, spatial shuffling, and permuted lesion masks.
- Real-map control reference metrics agree exactly with the original saved evaluation metrics.
- All 18 bootstrap summary rows reproduce; 2,000 replicates, seed 20260922; maximum numerical discrepancy 9.71445146547012e-17.
- Mask permutation reproduces, with no self-pairings.

These checks verify saved predictions and downstream analyses. They do not verify fresh model inference, original raw map generation, or outcome calculation from image pixels. The existing negative-control audit was already completed; do not issue a duplicate experiment.

## Interpretation

Negative-control performance is metric dependent, not uniformly superior. The existing classifier's low discrimination constrains interpretation of associations between explanation disagreement and quality outcomes. A null association in this cohort does not establish that EDI is unrelated to quality in other models.

The separate protocol-sensitivity bundle records practical, not exact, prediction parity: maximum error 0.012168526649475098 across 400 inputs, with one classification disagreement. This is distinct from the earlier factorial study's much tighter prediction parity. Do not transfer verification between model sets.

## Remaining research work

1. Inventory configuration-correct historical pairs, explicitly separating numerical reproduction, reference assignment, map/model identity, and transformation lineage. Define eligibility before comparing restricted and frozen rankings; compare on common support so changes in method/domain composition are not mistaken for provenance effects.
2. Inspect available classifiers and their training/validation provenance before selecting a prospective explanation-quality replication. Select the classifier using independent validation criteria before viewing replication-cohort outcomes, not by searching for a favorable EDI association.
3. If needed, create a separate, locked, six-method cohort with preserved maps and fixed melanoma targets. Verify existing models and input transformations before deciding whether retraining is necessary.
4. Keep completed prediction-linkage and matched-initialization uncertainty results. They establish cohort-specific associations and method-dependent reference contrasts; they do not demonstrate incremental predictive value.

## Files and hashes

Inspected repository HEAD: c5053d79314c58161a6a899bc88cd626f5c6816f.

Negative-control source output ZIP SHA-256: e3af56a020c42748b85d3b2cbe55dc03d59367b605ad9633e473143cbb38109c.

Original saved evaluation CSV.GZ SHA-256: 898901041e8e9c99bee50b9a7ee17e3918d09586bcdd25d734ca5cf7127ede40.

No training, attribution generation, or canonical table replacement was performed.
