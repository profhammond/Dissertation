# Annotated ISIC alignment evidence review — October 4, 2026

The evidence inventory completed successfully, but it does not yet authorize localization evaluation. It preserves the completed classification audit and does not change the running six-method cohort.

## Validation

Source: `edi_annotated_isic_alignment_evidence_v1_20261004T171021_734196Z_compact_bundle.zip`.

All 18 listed file sizes and SHA-256 checksums passed. All 100 locked image and mask hashes exactly match the previous v1.1 three-seed prediction audit. There are 100 unique image identifiers. Saved per-candidate best-resize errors and exact-interpolation flags agree with the exported per-interpolation diagnostics. Source image pixels are not contained in this bundle, so resize operations themselves cannot be independently recomputed locally. The six inspected feasibility CSV tables reported no read errors.

## Findings

| Evidence group | Images | Interpretation |
|---|---:|---|
| Current image and mask dimensions equal | 26 | Geometry agreement alone does not establish annotation provenance or registration. |
| Dimensions differ | 74 | Need documented image transformation and annotation correspondence. |
| Equal-dimension images with exact decoded-pixel alternative matches | 16 | These are same-size identity operations; they do not verify a downsampling transformation. There are 18 matching candidate files for 16 images. |
| Dimension-mismatched images with mask-sized candidate counterparts | 5 | Best resize agreement is approximate, not exact. |
| Dimension-mismatched images without a candidate in the bounded search | 69 | Absence applies only to inspected exports and sibling filenames, not all storage. |

Every one of the 23 candidate files has the mask's dimensions. The 18 exact candidate matches concern 16 of the 26 already equal-dimension images. The notebook's headline `with_exact_resize_link: 16` must therefore not be interpreted as 16 recovered downsampling histories.

The five differing-dimension candidate pairs have best mean absolute pixel errors (0–255 scale): ISIC_0001103 1.140469; ISIC_0000384 1.171534; ISIC_0000031 0.862154; ISIC_0000420 1.877134; ISIC_0000047 0.592032. INTER_AREA is the best tested interpolation for these five. JPEG encoding, image processing or another transformation could contribute to these differences; this audit does not establish their cause. No acceptance threshold was selected.

Maximum relative aspect-ratio difference across the 100 pairs is approximately 0.001312 (0.1312%). This supports compatible overall geometry, but does not prove that crops, rotations or image revisions are absent.

All ten contact sheets were inspected through two overview montages. Provisional contours broadly follow visible lesion regions; this is a visual plausibility observation rather than a quantified registration assessment or clinical annotation validation. Display uses a common square resize and nearest-neighbor masks. It cannot establish native coordinate lineage.

## Decision and next step

Keep localization eligibility pending for all 100 images, as specified before this audit. No images should be selected using classification performance or attribution outcomes. Do not replace current classification images with candidate originals: that would change the evaluated inputs.

The next targeted task is to recover the existing image-download/downsampling implementation and official annotation pairing documentation. Check whether the exact current image filenames derive from their matching official ISIC images through a documented resize/JPEG export, and lock the resulting coordinate transformation. Where lineage cannot be recovered, label a direct-resize analysis as provisional and assess sensitivity rather than claiming verified localization. The existing prediction audit and prospective six-method generation can continue independently.
