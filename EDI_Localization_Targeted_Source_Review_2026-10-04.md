# Targeted localization source review — October 4, 2026

The 100-image cohort selection is reproducible. Its feasibility gate did not establish image–mask coordinate lineage.

Source: `edi_localization_targeted_source_export_v1_20261004T175610_054535Z_compact_bundle.zip`. All seven file checksums and sizes passed. Three notebooks supplied 147 source cells with no source truncation; 16 cells matched the audit's search pattern. These are source exports, not reruns of the original notebooks.

## Cohort-builder findings

`EDI_Paired_Localization_Cohort_Builder_Readiness_Audit_V2.ipynb` has SHA-256 `2bacea2c186f02150963ba8a563a1290f98270c29fa60c37eb44a431d4ec32d0`.

Cell 2 normalizes filenames by extracting an ISIC identifier. Cell 6 prioritizes membership in `datasets/cached_downloads/ISIC2019/images` before exact-stem and downsampled flags. Thus, an image in that preferred folder can be selected over an original-named alternative in another folder. This is a deterministic path-selection policy, not evidence of pixel-equivalent aliases.

Cell 8 records native image and mask dimensions but defines `pair_valid` by readability alone. It does not gate inclusion on dimension equality, a documented crop/resize/orientation chain, or registration. Cell 12 sets `localization_analysis_authorized` from cohort size, and cell 14 resizes masks directly using nearest-neighbor interpolation for overlays. Consequently, those historical status flags support the feasibility procedure's own checks; they do not establish the stronger localization-alignment claim currently being audited.

Using the saved candidate manifest and recovered selection procedure, the reviewer independently reproduced all 100 ordered selected identifiers, image paths, mask paths, labels and lesion-size strata. The selection uses seed 20260910, 50 images per class, and 17 small/17 medium/16 large lesions within each class. The comparison accounts for pandas categorical-versus-string storage without changing values. Selection reproducibility does not validate original diagnostic labels independently or establish train/test independence.

## Other source notebooks

`Notebook 02 — Artifact and Lesion Mask Preparation.ipynb` handles downstream PH2 lesion-mask copying, nearest-neighbor mask resizing, algorithm-generated artifact masks and preservation masks. It does not establish the producer of the locked ISIC2019 downsampled image copies. Algorithm-generated hair/artifact masks must not be described as independent manual annotations.

`NB11_Cross_Domain_EDI_Generalization_Analysis.ipynb` contains downstream aggregate analyses rather than the missing image-downsampling producer. No downsampled-image creation code was found in these three fully exported source notebooks.

## Decision and next task

Keep the fixed 100-image cohort and completed three-seed prediction audit unchanged. Mask extraction provenance is supported by the preceding archive audit; image coordinate correspondence remains pending. Neither readable pairs nor resized overlays should be upgraded to verified localization eligibility.

Further general notebook searches are unlikely to resolve this efficiently. The next useful evidence is the paired official ISIC 2018 training-image archive or recorded dataset acquisition/preparation source that created the current ISIC2019 image copies. If already available, inspect only the 100 relevant official input members and compare them with the locked images, preserving archive/member hashes and a declared coordinate transform. A newly acquired official image comparison would be new reference evidence, not proof of the historical producer. If historical lineage cannot be recovered, any direct-resize localization analysis should explicitly remain provisional and include coordinate-transform sensitivity checks. The ongoing prospective six-method cohort remains independent of this issue.
