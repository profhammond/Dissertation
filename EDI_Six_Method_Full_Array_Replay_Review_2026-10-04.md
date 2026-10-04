# Six-method full-array replay review — October 4, 2026

## Decision

PASS. The remaining full-cohort saved-array verification step is complete. This report supersedes the pending full-array verification status in `EDI_Concurrent_Bundle_Audit_2026-10-04.md`; it does not change the six-method results or the earlier audit findings.

## Verified evidence

All six checksum-listed files pass. All eight locked input/source files match the previously reviewed six-method bundle. The returned replay runner matches the notebook's delivered source hash. Every task, array fingerprint, validity flag, fallback flag and comparison endpoint reconciles with the generation bundle.

| Check | Result |
|---|---:|
| Saved arrays replayed on Drive | 2,160 |
| Nonconstant defined maps | 2,127 |
| Constant maps retained | 33 |
| Planned pair outcomes verified | 1,440 |
| Defined metrics reproduced | 1,394 |
| Undefined pair outcomes retained | 46 |
| Maximum normalized-map discrepancy | 1.33e-15 |
| Maximum IG/SHAP RGB aggregation discrepancy | 0 |
| Maximum Pearson discrepancy | 1.52e-14 |
| Maximum SSIM discrepancy | 3.33e-16 |
| Maximum EDI discrepancy | 3.86e-15 |

The replay independently reconstructs bilinear resizing and normalization with NumPy, and SSIM using SciPy uniform filters; it does not call the attribution engine's comparison-map or metric functions. Numerical discrepancies are below the fixed tolerances (normalization 1e-12, paired metrics 1e-10). The review recomputed exported differences and reconciled all rows against the earlier generation bundle.

The 33 constant maps and 46 undefined pairs remain ScoreCAM outcomes on non-melanoma images. They are retained declared outcomes, not failed audit computations. Common support remains 97/120 model/image observations per preprocessing condition, with 60 melanoma and 37 non-melanoma observations. That imbalance and GradCAM's valid signed-fallback maps remain material sensitivities.

## Scope and limitations

Full raw arrays were read on Drive by the independent CPU replay notebook. This compact return bundle contains complete replay reports, source and fingerprints rather than those arrays. Direct local raw-array reproduction remains limited to the original 36-map sample; full-array numerical agreement is evidenced by the locked, independently implemented Colab replay and reconciled reports. No training, model inference or attribution regeneration occurred.

Passing this audit validates numerical consistency of current saved assets under the declared implementations. It does not establish explanation correctness, clinical usefulness, historical map identity or incremental predictive value. GradCAM++ remains the documented approximation, and EigenCAM remains class-independent.

## Combined evidence status

- The six-method fixed-model HAM cohort is complete and its saved-array replay passes. Available and common-support method summaries can be analyzed with their coverage and fallback limitations.
- The later matched-initialization study passes reproduction of all 720 maps and 2,160 comparisons. Recorded initialization digests and historical generating-model identity retain the earlier limitations.
- The verified prospective ISIC localization analysis is complete: absolute lesion-mass-change associations are positive for both CAM methods, while directional results depend on method/fallback handling. Secondary prediction-change associations are cohort-dependent and do not establish added value.

The next task is a joint analytical review, including uncertainty for six-method comparisons on matched support, before selecting dissertation revisions. No dissertation source changes were made by this audit.
