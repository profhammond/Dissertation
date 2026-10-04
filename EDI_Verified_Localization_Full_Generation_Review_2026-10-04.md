# Verified localization full-generation review — October 4, 2026

The full prospective generation bundle passed the structural and sampled numerical audit. Scientific analysis under the frozen v1.1 design is the next step.

Source: `edi_verified_localization_cam_isic100_v1_compact_bundle.zip`.

All 134 listed file checksums and sizes passed. The run fingerprint independently reproduces from its configuration. Embedded attribution-engine and runner source hashes match the run lock. All 3,132 task signatures independently reproduce from the run fingerprint, model/input hashes and task identity.

## Completeness and pairing

The bundle contains 3,132 unique map records, 1,566 unique prediction records, 9,396 unique map/raster localization rows and 3,420 comparisons (2,088 preprocessing pairs and 1,332 image-version pairs). Every pair endpoint has the correct image, model, seed, method, condition and version relationship. All pair prediction changes, class-switch flags, EDI formulas and raster-specific lesion-mass changes independently reproduce from the exported endpoint tables. No planned map is constant; all metrics are defined in this generated cohort.

All 300 current-original predictions match their previously audited predictions within the unchanged 1e-5 tolerance; maximum discrepancy is approximately 1.04308e-6. All bridge parity errors are zero. Six fresh map repeats have zero measured relative error. The maximum fresh-versus-checkpoint relative error is approximately 2.99096e-6, also below 1e-5. Small numerical variation across executions is therefore present without a parity violation.

## Array checks and limitation

The prespecified sample contains 108 maps from the four smoke cases, all seeds, input versions and conditions, plus their mask rasters. Array hashes and normalization/fallback status reproduce. All 324 sampled localization outcomes reproduce with maximum discrepancy 4.44e-16; sampled normalized maps differ from an independent bilinear-resize implementation by at most 1.11e-15. All 108 sampled pair metrics reproduce with maximum discrepancy 4.33e-15.

The 108 sampled maps were reused from the passed smoke. This checks preservation, export and arithmetic but is not an independent array-level check of newly generated cases. The remaining full arrays stay on Drive; their reported hashes/signatures and row relationships have been inspected, but those arrays were not independently opened or recalculated locally. Any claim of exhaustive raw-array numerical verification would exceed this audit. If a further array audit is needed, select additional cases deterministically by task identity rather than by observed EDI/localization outcomes.

## Signed fallback

There are 137 signed-fallback maps, all Grad-CAM: 56/900 official-input Grad-CAM maps and 81/666 current-copy Grad-CAM maps. Grad-CAM++ has zero fallbacks. The full cohort includes 3,132 maps, so the overall fallback frequency is 4.37%.

Signed fallback normalizes the signed map when its ReLU map is constant. It does not convert a map into independent evidence of positive class-specific lesion relevance. Report fallback coverage and analyze the localization/EDI relationship both with all declared maps and with a clearly labeled fallback-free sensitivity, preserving all excluded rows in the audit ledger. Do not infer better explanation quality from lower EDI or greater lesion mass alone.

## Next analysis

Follow the frozen design: official-input primary associations; current-copy/image-version and byte-identical-subset sensitivity; all three fixed seeds; mask-raster sensitivity; image-clustered, class-stratified 5,000-draw uncertainty. Report classification context, defined/common method support and signed-fallback coverage. Treat mask localization as lesion correspondence, not perturbation faithfulness. Reference-input predictions are new prospective records and must not replace historical current-copy predictions. The separate six-method HAM cohort remains independent.
