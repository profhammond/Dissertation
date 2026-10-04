# Completed pair-protocol and HAM Diffusion review
Reviewed 3 October 2026. Original artifacts unchanged; no retraining, map generation or canonical integration.

## Recorded-pair protocol run
15360 unique source rows, 30720 attempts (two protocols), all paths calculated. IG:3840 complete-target matches; SHAP:3840; Eigen-CAM:960; Score-CAM:960. Both protocols produce the same match set. These are 9600 unique matches, not 19200 independent reproduced comparisons. All complete-target rows match tolerance 1e-4. Of the unique matches,7200 carry baseline-ID mismatch flags;2400 do not. No model-generation identity was verified.

5760 remaining Eigen-CAM/Score-CAM rows (128/160/192 resolutions) have absent target Pearson, SSIM and EDI values in the exact input ledger. They are not demonstrated numerical mismatches. Legacy SSIM is nonfinite on these small maps; adaptive metrics are finite, but targets remain absent. Earlier adaptive repair audits used different target exports and must not be pooled or compared as if their target coverage were identical. Reconcile against the preserved corrected internal manifest before further reproduction claims. Canonical integration remains unauthorized.

Source ledger SHA256: fa57271c5c3e5a13f68775cef3f11d9632cfcecdb3e464bc1232b5ff2c1640cd.

## HAM Diffusion notebook evidence
Notebook SHA256:2f99b9fd15845a2b89793fcd28c3e8aa46e49af0b32567194d9598635c64a3a2.
Retained configuration/output identifies ham_diffusion_r224_20260519_193809. Cell45 (execution_count34) constructs datasets with batch8,shuffle512, no flip and no apply_preprocessing call. Cell53(count39) shows 902 steps and epochs1–15 of a20-epoch cap. Cell55(count40) shows epochs1–6 of a10-epoch cap. Cell66(count46) prints a saved-model path matching the inspected r224 archive. CONFIG retains batch_size32. Thus the notebook offers converging source/output evidence of a pipeline/config discrepancy, but retained outputs and counts are not immutable historical execution proof.

The source defines tv_diffusion and apply_preprocessing but has no other recovered invocation applying the transform to training inputs. Do not assert that the saved weights definitely omitted diffusion; reconcile full run records and input paths. Do not generalize this r224 evidence to all resolutions. Treat matched-preprocessing causal interpretations as limited until reconciled. No results were deleted or replaced.

## Next actions
1. Recover finite target metrics for the5760 ledger rows from the exact preserved corrected internal manifest; retain both source hashes and compare keys without guessing.
2. Reconcile HAM Diffusion r224 source/output evidence with saved predictions, metrics and input provenance. Confirm whether the model was trained on transformed inputs or represents a mislabeled condition.
3. Preserve these results in the dissertation audit repository and update the issue register. Keep augmentation qualification and avoid universal batch-size statements until this exception is resolved.
