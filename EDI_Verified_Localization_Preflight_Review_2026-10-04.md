# Verified localization CPU preflight review — October 4, 2026

The preflight passed. Prediction/attribution generation remains behind the planned smoke-test gate; `generation_ready: false` is expected.

Source: `edi_verified_localization_preflight_v1_20261004T191012_930336Z_compact_bundle.zip`.

All 14 listed file sizes and checksums passed. The frozen design hash is `f028186bc51bf1a738ed6b76e86f66d32a84dfac49c761851e60cc940f3edafb`. The recorded archive hash matches the reviewed official reference acquisition. All 203 recorded asset checks (three models, 100 current images and 100 masks) match their expected hashes.

The task plan has 3,132 unique map tasks: 1,800 official-input tasks and 1,332 current-copy tasks, two methods, three seeds, three conditions, fixed target 1. The 522 transformed input keys are unique. All tasks join uniquely to their planned input with matching label and array hash. Every endpoint in the 2,088 preprocessing pairs and 1,332 image-version pairs is present and has the correct image, model, seed, method and condition relationship. The 26 byte-identical current copies explicitly alias official inputs. Planned prediction records total 1,566.

All 100 masks have nonempty, nonfull rasters under all three declared raster paths. The compact bundle contains two mask-array samples. Their shape, uint8 dtype, binary values, array hashes, lesion fractions and pairwise disagreement fractions independently reproduce from the saved arrays. Across the complete mask ledger, nearest-versus-area-threshold disagreement averages 0.004221 (0.4221% of pixels), with maximum 0.028958 (2.8958%). Direct-versus-via-current nearest-neighbor disagreement averages 0.000910 (0.0910%), with maximum 0.013213 (1.3213%). These are raster differences, not estimates of annotation or registration error.

The complete native source and transformed input arrays remain on Drive, rather than in this compact bundle. Consequently, all 522 image transforms and all native-to-mask raster operations were not independently recomputed locally; the provided ledger and two saved mask samples support the stated checks. A subsequent smoke test must verify selected transformed input bytes/arrays and preserve prediction parity and model-bridge checks.

Next: generate a small prespecified prediction/CAM/localization smoke test using the established attribution engine, retaining constant maps as audit outcomes and checking localized-mass arithmetic independently. Use all three fixed seeds on selected cases spanning labels and byte-identity groups. No models need retraining, and no full localization map run should begin before that smoke bundle is reviewed. The ongoing six-method cohort is independent.
