# Official ISIC reference comparison review — October 4, 2026

The reference acquisition supplies counterparts for every locked image. It establishes direct official-image identity for 26 pairs; the exact historical transform of the other 74 remains unverified.

Source: `edi_isic_reference_image_archive_v1_20261004T183432_017721Z_compact_bundle.zip`.

All ten listed checksums and file sizes passed. All 100 image/mask fingerprints match the preceding prediction audit. There are 100 unique comparison rows. Reference-image hash equality with the locked image hashes independently agrees with every saved byte-match flag. Best-resize summaries and exact-interpolation flags reproduce from the per-interpolation export. The original reference pixel arrays are not in the compact bundle, so resize calculations themselves were not independently recomputed locally.

The acquisition record documents an HTTPS download from the official ISIC archive endpoint, complete at 11,165,358,566 bytes, with archive SHA-256 `80f98572347a2d7a376227fa9eb2e4f7459d317cb619865b8b9910c81446675f`. Its ETag is a multipart object identifier, not a SHA-256 checksum. The supplied archive hash is locally computed; it has not been compared with a separately published cryptographic checksum. The conservative automatic authentication/eligibility flags remain false.

## Findings

- All 100 official image members have the same native dimensions as the corresponding locked masks. The preceding audit tied all 100 masks to unique members of the saved official ground-truth archive.
- Twenty-six current images are byte-identical to the official reference inputs. Their coordinate identity does not require reconstructing a downsampling transform. The four interpolation tests in these cases are same-size identity operations, not evidence of downsampling history.
- Seventy-four current images differ in resolution and bytes. None exactly matches a tested direct resize. Mean absolute errors on the 0–255 pixel scale range from 0.592032 to 3.076810, with mean 1.471898 and median 1.376259; RMSE ranges from 0.984499 to 4.213093. INTER_AREA is selected as best for all 74 under the declared tie-breaking rule and is strictly better than the other three settings for 73.
- Approximate agreement is consistent with reduced-resolution copies of the official images, but these tests do not identify the complete historical resize/JPEG pipeline or exclude small coordinate differences. No acceptance threshold has been chosen.
- The 26 byte-identical images comprise 16 melanoma and 10 non-melanoma cases. They are a provenance-defined subset rather than a balanced substitute for the original 100-image evaluation cohort.

## Decision and next step

The earlier missing-reference problem is resolved. Stop broad inventories and source searches. Preserve the current locked cohort and classification outputs.

For the 26 byte-identical inputs, official image identity and matching annotation identifier/dimensions now provide a direct pairing basis. This does not turn localization into a measure of clinical correctness or automatically validate the attribution evaluation implementation. For the remaining 74, any evaluation on current copies should explicitly describe the assumed coordinate resize and assess sensitivity.

A useful next step is to freeze the localization design before generating new maps: report the byte-identical subset separately, and evaluate the full cohort with declared direct-resize assumptions and a reference-input sensitivity arm if computationally justified. Reference-input inference/maps would be new prospective outcomes and must not be merged into historical predictions. No cohort or seed should be chosen based on favorable performance or localization results. The independent ongoing six-method 40-image cohort remains unchanged.
