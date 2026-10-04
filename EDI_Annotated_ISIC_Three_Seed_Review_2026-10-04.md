# Annotated ISIC three-seed inference review v1.1 — 2026-10-04

Bundle SHA-256: bd18be29eb1a99d3b4bfe5cec89fbde5e038a1e1d3de2c1f653012f9c81fc370. All 14 checksum entries verify. Independently reproduced all classification summaries from 300 unique predictions; maximum discrepancy 5.55e-17. The 100 image IDs and labels agree with the prior saved-prediction cohort. All current model hashes and post-run asset checks pass. Repeated inference error is zero for each seed's tested image.

| Seed | ROC-AUC | Average precision | Brier | Sensitivity at 0.5 | Specificity at 0.5 |
|---|---:|---:|---:|---:|---:|
| 42 | 0.7176 | 0.7614 | 0.2900 | 0.20 | 1.00 |
| 1337 | 0.7312 | 0.7715 | 0.2887 | 0.18 | 1.00 |
| 2026 | 0.6968 | 0.7223 | 0.3123 | 0.12 | 0.98 |

All three preselected models have descriptively higher ROC-AUC than the older model's 0.4164 on the same 100 labeled images. This is an observed comparison without an inferential superiority test. They still have low melanoma sensitivity at the fixed threshold and do not establish reliable clinical classification. On this balanced cohort, all three Brier scores exceed the 0.25 loss of a constant 0.5 predictor; that observation does not identify calibration as the sole cause. No threshold or model was selected using these outcomes.

No exact image-ID or path overlap with the existing HAM training/validation splits was detected. The full-cohort and screened-subset metric rows are identical because all 100 images meet this limited screen; they are not separate experiments. Byte-alias, lesion and patient overlap screening remains incomplete. Labels were reconciled with prior recorded labels, not independently with original diagnostic metadata.

All masks are nontrivial binary arrays. Native dimensions match for 26 pairs, differ for 74 downsampled-image pairs. Correct spatial alignment is not established by this audit, even for equal-size arrays. No mask resizing or localization score generation occurred.

## Next work

Retain all three models for any prespecified replication; do not select seed 1337 because its evaluated AUC is largest. The same model trio can support a separate fixed-model faithfulness pilot, with limitations from cohort performance reported. Localization additionally requires recovering image/downsampling/orientation lineage for the independent masks.

Next independent CPU task: inspect existing source records and available original-resolution images to verify alignment for the 74 downsampled pairs and correspondence for the remaining 26. Preserve the 100-image cohort and original masks. Do not assume arbitrary resizing proves alignment. The ongoing six-method HAM experiment remains unchanged and uses a different 40-image cohort.
