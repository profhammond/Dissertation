# ISIC reference-image archive review — October 4, 2026

The audit completed successfully but found no reference images within its declared search scope. This is a completed negative inventory, not a failed experiment and not evidence of misaligned masks.

Source bundle: `edi_isic_reference_image_archive_v1_20261004T180755_459039Z_compact_bundle.zip`.

All nine listed file checksums and sizes passed. The 100 unique locked image/mask fingerprints exactly match the completed v1.1 prediction audit. The search visited 47 directories, exhausted its queue, and recorded no errors or depth-limit exclusions. It found zero matching training-input archives and zero matching extracted reference-image files; both comparison and reference inventories are empty.

The search covered the existing datasets, localization-feasibility and named ISIC2018 folders, recognizing ISIC2018 Task1/Task1-2 training-input names. It did not search arbitrary archive names, other storage roots, remote sources or every possible reference dataset. `validation_passed: true` means the inventory procedure passed its checks; it does not mean reference-image comparisons or localization alignment passed. The bundle correctly records `reference_evidence_found: false` and `localization_eligibility_verified: false`.

## Decision

The current evidence chain supports official-mask extraction and reproducible cohort selection. It has not established the coordinate lineage of the locked image copies. Another similar local inventory would add little evidence.

The next useful step is to obtain the official paired ISIC2018 Task1-2 training-image reference, retain acquisition metadata and hashes, and compare the 100 locked images against its corresponding members under declared transformations. This would add new reference evidence without proving the identity of the historical image-downsampling producer. Preserve the current images, labels and cohort; do not overwrite them with downloaded originals or silently substitute new inputs into completed predictions.

If acquiring that reference is impractical, retain historical localization findings with explicit direct-resize assumptions and defer stronger verified-localization claims. The independent six-method fixed-model study and classification/prediction analyses can proceed. No attribution or model rerun is justified solely by this negative inventory.
