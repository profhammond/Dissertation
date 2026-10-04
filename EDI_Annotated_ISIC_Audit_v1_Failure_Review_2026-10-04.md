# Annotated ISIC audit v1 gate correction — 2026-10-04

Input bundle SHA-256: da8eb211612d7f2fe26eec2d063cd04eb77c1c1650af45bbda0553c54a25e583. All six checksum entries verify.

The notebook stopped before model loading/inference. All 100 image/mask pairs were readable with nontrivial binary masks. Twenty-six pairs have identical native dimensions; 74 do not. All 74 mismatch records use downsampled image filenames paired with masks at another resolution.

The original equality gate incorrectly blocked classification for a localization-geometry issue. Equal image/mask dimensions are not required for image-only classification. This finding does not establish that the masks are invalid, and it does not establish correct spatial alignment after resizing.

Version 1.1 retains all original geometry flags and adds exact SHA-256 checks against the 100 image/mask fingerprints from v1. It permits classification inference without resizing masks or declaring localization alignment. Annotation alignment remains unverified and needs image transformation lineage before any new localization evaluation. The cohort, labels, three model seeds and fixed threshold remain unchanged. No classification outcomes were generated before the amendment.

The original failed status remains authoritative for v1; do not overwrite it as passed.
