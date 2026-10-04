# Localization smoke v1.1 review — October 4, 2026

The corrected smoke passed. Full prospective generation can now be implemented under the frozen v1.1 design and reviewed preflight, preserving all planned rows and undefined outcomes.

Source: `edi_verified_localization_smoke_v1_1_20261004T201020_592134Z_compact_bundle.zip`.

All 123 listed file checksums and sizes passed. The exported attribution engine exactly matches the established engine source. There are 108 unique planned/generated maps, 54 predictions and six repeat checks on the same four prespecified cases and three seeds. All maps were nonconstant, with no signed fallbacks in this sample. This does not guarantee full-cohort map validity.

Reported bridge parity error is zero. All 12 saved-current-original prediction parity checks are present and below 1e-5; maximum discrepancy is 1.11e-16. All six raw-map repeats have zero measured absolute and relative difference. The corrected inputs therefore resolve the observed v1 prediction-parity failure for these smoke cases without changing tolerance. The failed v1 run remains an audit record.

Independent local recomputation from all saved arrays verifies raw/normalized array hashes, bilinear resize/normalization and fallback status. Maximum normalized-map discrepancy is 1.11e-15. All 324 localization rows (108 maps × three mask rasters) reproduce lesion mass, excess mass and tie-preserving peak fraction, maximum discrepancy 4.44e-16. All 108 pair rows reproduce Pearson, SSIM and EDI, maximum discrepancy 4.33e-15. These pair rows comprise 72 preprocessing comparisons and 36 image-version comparisons; they are implementation checks on four images, not independent scientific evidence about the full cohort.

Next: a resumable full generator bound to the exact v1.1 design/preflight/engine and model/input hashes. Preserve complete arrays on Drive, durable checkpoints, progress, per-map localization, per-pair predictions and a compact review bundle with a prespecified array sample. Validate all 3,132 map tasks, 2,088 preprocessing pairs, 1,332 version pairs and 1,566 prediction records before interpreting outcomes. Keep attribution-generation errors distinct from declared constant-map outcomes. Analysis should follow the frozen image-clustered uncertainty and mask-sensitivity specification.
