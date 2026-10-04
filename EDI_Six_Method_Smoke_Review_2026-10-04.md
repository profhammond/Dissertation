# Six-method implementation smoke review — 2026-10-04

Bundle SHA-256: 56ee54dac3aa556ae8f6d8a4d7eb3f1fc5fca2748f4382547ed335b53b63de93.

## Outcome

Execution and saved-array arithmetic verified, with one retained degenerate Score-CAM outcome. Strict technical_smoke_passed=False and full_generation_ready=False are appropriate under the original gate. Do not bypass the gate or change the selected images.

- All 85 exported file sizes and SHA-256 values verify.
- All 36 map tasks executed without method exceptions; 35 nonconstant maps, one identically zero Score-CAM map.
- All six deterministic repeats have exactly zero raw-array discrepancy.
- Six current predictions agree with saved probabilities; maximum absolute error 4.470348e-7, below the predetermined 1e-5. Reconstructed CAM graph predictions match the native classifier exactly.
- All 11 post-run source/report asset checks report unchanged bytes.
- Target layer: efficientnetb0/top_conv, shape 7 x 7 x 1280; classifier tail GAP, dropout, dense.
- Maximum IG absolute completeness residual 0.0045934674, below the predetermined 0.02. The linear IG control passed. This does not establish integration convergence for all prospective images.
- Maximum SHAP additivity residual about 5.55e-17. Additivity does not certify accuracy of the finite-budget hierarchy attribution.

## Independent saved-array checks

Independently reproduced raw-to-comparison-map interpolation, ReLU/signed fallback, per-map normalization, and raw RGB-channel summation for IG/SHAP. Maximum normalized-array discrepancy 1.11e-15; tensor aggregation discrepancy zero.

Recalculated all 22 defined paired comparisons: maximum errors Pearson 1.11e-15, SSIM 3.33e-16, EDI 2.29e-16. Both undefined pairs retain absent metrics; no fabricated zero EDI.

## Degenerate outcome requiring diagnosis

ISIC_0028563, baseline input, seed 42, Score-CAM has an exactly zero raw map. Its baseline-versus-DullRazor and baseline-versus-Telea EDI comparisons are therefore undefined. This is one of six Score-CAM tasks and two of 24 planned smoke comparisons, not evidence about invalid-map prevalence in the full cohort.

The implementation uses positive-clipped probability increase relative to a black input as channel weights. The black melanoma probability is 0.079739, versus original image probability 0.014066. This makes zero clipped channel weights a plausible explanation, but the individual masked-channel scores were not exported. Do not assert the mechanism as verified until those scores are inspected.

Next run a bounded diagnostic for this exact model/image only: preserve all 1,280 channel-mask probabilities, black reference, unclipped and clipped weights, and the resulting raw array; verify reproduction of the saved zero map. No other method or image needs rerunning. Any alternative weighting scheme is a separately identified prospective implementation/sensitivity, not a repair of this saved result. Preserve the original specification and outcome.

## Runtime identity

TensorFlow 2.20.0; SHAP 0.52.0; NumPy 2.1.3; pandas 2.2.3; scikit-image 0.25.2; OpenCV 4.14.0; Python 3.13.15. GPU was available. The supplied runtime contains exact SHAP module fingerprints. Future continuation must preserve or explicitly report runtime differences.

No evidence here certifies attribution faithfulness, clinical validity, or historical generating-model identity. No full cohort or new training was run.
