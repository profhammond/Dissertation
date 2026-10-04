# Score-CAM diagnostic review — 2026-10-04

Diagnostic PASS. Bundle SHA-256: 7b9a9b0c0e1b884985ac07e168740843862670166d2a84590fcd8a59306272d1.

All eight checksum entries verify. All 1,280 channel rows are unique, finite and used. No source assets changed. Same runtime and graph parity verified; raw zero-map reproduction error is exactly zero.

For ISIC_0028563 original input, baseline seed 42:
- Original melanoma probability: 0.01406628545.
- Black-input reference probability: 0.07973944396.
- Channel-masked probabilities: 0.00034174093 to 0.02360611223.
- Every channel-masked probability is below the black reference; maximum probability increase is -0.05613333173.
- The declared positive-clipped increase rule gives zero weight for every channel and therefore an exactly zero map.

This verifies an expected degeneracy of this specified Score-CAM weighting variant on this input, not an execution exception. Do not describe the implementation as a universally equivalent implementation of every published Score-CAM variant. Report the positive-clipped black-reference weighting explicitly. No historical map is repaired by this diagnostic.

The original smoke technical gate remains failed because it required every map to be nonconstant. Its recorded status must not be rewritten. Following mechanism verification, a separate full-run acceptance policy can permit retained undefined outcomes, without changing the attribution formula, image cohort or original results.

## Prespecified full-run invalid-outcome policy

1. Keep the entire locked 40-image cohort, all three baseline seeds, three input conditions and six methods. Preserve all 2,160 planned map tasks and all 1,440 comparisons, including constant maps and method failures.
2. Preserve raw arrays and diagnostics. For a constant/undefined pair, store missing Pearson, SSIM and EDI with an explicit reason; never replace with zero, maximal drift or another method's map.
3. Report valid-map and defined-pair rates per method, condition, seed and class. Report planned and evaluable denominators separately. The smoke's one degenerate map is not a prevalence estimate for the full cohort.
4. Summaries using available pairs must disclose changing support. Between-method comparisons must use explicitly constructed common image/seed/condition support and report its size and exclusions. If common support is inadequate, report the coverage limit rather than force a six-method ranking.
5. Keep input/model hash, prediction/graph parity and finite raw-array checks as technical requirements. Declared constant outcomes are permitted; software exceptions or nonfinite arrays block readiness and require investigation. IG completeness failures must be audited and flagged, not silently dropped or repaired by threshold relaxation.
6. Any alternative Score-CAM weighting is a separately named prospective sensitivity with its own locked implementation. Do not select it to eliminate this observed failure or overwrite the positive-clipped variant.

This policy amendment addresses an observed, verified method degeneracy and must be disclosed as made after the two-image smoke, before the full cohort. It is not a claim that the original all-valid gate passed.

Next deliverable: a resumable full-cohort generation notebook using unchanged methods, exact runtime/source identity checks, original smoke asset identities, and this explicit undefined-outcome policy. Preserve the separate prospective output corpus; do not merge it into the historical frozen manifest.
