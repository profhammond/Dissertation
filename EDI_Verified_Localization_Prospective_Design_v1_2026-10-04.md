# Prospective localization and explanation-quality replication — design v1

Frozen October 4, 2026, after reference-image acquisition and classification-context audits, before new reference-input predictions, maps or localization outcomes. This is an internal dated analysis specification, not an externally preregistered study.

## Question and scope

Does preprocessing-associated EDI relate to changes in lesion localization under documented image–mask correspondence, and do those relationships depend on image version, attribution method or fixed trained model?

EDI measures map disagreement. Localization measures spatial correspondence with a lesion annotation. Neither alone establishes faithfulness, diagnostic correctness or clinical usefulness. Added predictive value is not established by a correlation between these quantities.

The 100-image cohort is fixed: 50 melanoma and 50 non-melanoma with the existing labels and original selection order. Use all three existing baseline models, seeds 42, 1337 and 2026, regardless of observed performance. The completed classification audit found low sensitivity at threshold 0.5; retain this context rather than selecting the best seed. Image-ID/path training overlap checks passed previously, but patient/lesion and byte-alias independence were not exhaustively verified.

## Primary reference arm

Use the exact 100 official ISIC2018 Task1-2 training-input members and corresponding locked official mask members. Verify reference archive SHA-256 `80f98572347a2d7a376227fa9eb2e4f7459d317cb619865b8b9910c81446675f`; preserve per-member image hashes from the completed reference comparison. Verify mask hashes against the existing 100-mask ledger and native dimensions against reference images.

Read RGB uint8; apply the locked preprocessing at native image resolution, then resize to 224×224 with OpenCV INTER_AREA. Conditions: original, dullrazor and telea. The original native-coordinate mask applies to all three conditions; no image cropping or geometric warping is introduced.

Primary mask raster: threshold the native grayscale mask at >0, then resize its uint8 binary array directly to 224×224 using INTER_NEAREST. Sensitivity raster: resize the same binary mask as float32 using INTER_AREA, then threshold at >=0.5. Save both arrays, hashes, lesion fractions and disagreement fraction. Empty/full mask rasters are audit outcomes; do not silently remove images.

Methods: the two CAM implementations already smoke-tested for the six-method study. Use the exact locked source, including the declared Grad-CAM++ approximation based on powers of first gradients. Explain melanoma output index 1 for every image. Preserve raw maps, normalized comparison maps and normalization/fallback status. Apply the same EDI settings as the ongoing six-method cohort: full pixels, Pearson and SSIM window 7/data_range 1, no clipping of negative SSIM.

## Historical-copy sensitivity arm

For the 74 images whose current copies differ from official inputs, use the existing locked current image bytes. Apply identical native-input preprocessing followed by resize to 224. Use direct native-mask-to-224 rasterization as above, explicitly assuming full-frame coordinate correspondence. This assumption is not established by historical producer evidence.

Also preserve a mask-raster sensitivity that resizes the native binary mask to the current copy's native dimensions using INTER_NEAREST and then to 224 using INTER_NEAREST. This tests rasterization path, not unidentified crops or rotations.

The other 26 current inputs are byte-identical to official inputs: reuse their reference-arm computation after checking task/model/settings identity. Report these 26 separately as a provenance-defined subset (16 melanoma, 10 non-melanoma); do not present them as a balanced cohort or choose additional cases based on outcomes.

Reference-input and current-copy predictions/maps are distinct prospective observations where inputs differ. Never substitute reference predictions into the completed current-copy classification audit.

## Size and comparisons

| Arm | Unique images | Models | Conditions | Methods | Maps | Original-to-preprocessing EDI pairs |
|---|---:|---:|---:|---:|---:|---:|
| Official reference | 100 | 3 | 3 | 2 | 1,800 | 1,200 |
| Additional current-copy sensitivity | 74 | 3 | 3 | 2 | 1,332 | 888 |
| Total distinct generation tasks | 174 image-version records | | | | 3,132 | 2,088 |

There are 1,566 distinct model/input prediction records. For the 74 images, reference-to-current comparisons add 1,332 within-condition map comparisons without requiring additional maps. These image-version contrasts must be reported separately from preprocessing contrasts. Counts are planned tasks, not guaranteed defined outcomes.

## Localization outcomes

Primary: lesion attribution mass, sum of nonnegative normalized-map values inside the lesion mask divided by total map mass. Also report excess mass over the lesion's pixel fraction. A constant positive map therefore does not appear better than spatially uniform allocation. A zero-total-mass map has undefined localization mass and an explicit reason.

Secondary: peak localization as the fraction of all maximum-valued pixels inside the lesion mask. Preserve ties rather than selecting a favorable maximum. Constant maps are invalid explanation-localization outcomes, even if a numerical tie fraction can be computed. These metrics describe agreement with lesion boundaries, not diagnostic feature correctness.

For each original-to-preprocessing pair preserve baseline and comparison localization, signed localization change (comparison minus original), absolute change, EDI components, EDI, melanoma probabilities, probability change, class switch, correctness transition, model hash, image hashes and map hashes.

## Analysis

Report all three seeds separately and a pooled descriptive summary with seeds treated as fixed evaluated models. Preserve paired image records across seeds, methods and conditions. Primary associations are Spearman correlations of EDI with signed and absolute lesion-mass changes, separately by method and preprocessing condition, for the official arm. Results on the full current-copy cohort, the 26 identical-image subset, the 74 differing-image subset and alternate mask rasters are sensitivity analyses, not independent replications.

Use 5,000 image-clustered bootstrap draws, seed 20261004, resampling within true-label classes and carrying every sampled image's seed/method/condition records together. Report 95% percentile intervals and defined cluster counts; undefined/constant bootstrap correlations remain explicit. This quantifies image sampling variability for the fixed three models, not a population distribution of training seeds. Associations are exploratory; avoid significance-based ranking across multiple contrasts.

Report per-method available support and a common two-method support sensitivity. Retain every planned task and all undefined rows. State that complete-case estimates may be affected by nonrandom undefined maps. Report coverage and signed-fallback frequencies by arm, seed, method, condition and label.

Also report discrimination, sensitivity/specificity at the unchanged 0.5 threshold, and Brier score on each input version. Do not tune thresholds on these evaluation images. An input-version performance difference is not evidence that one attribution method is better.

## Faithfulness and incremental value

This stage is a localization replication, not a new perturbation-faithfulness experiment. Existing deletion/insertion evidence retains its prior limitations. Specify a separate perturbation design only if localization and prediction analyses leave a concrete unanswered question; do not call lesion mass a faithfulness score.

Correlations with prediction changes or localization do not establish incremental value. An added-value claim requires a prespecified outcome, a prediction-information comparator and image-grouped validation, with all model/condition records for an image in the same partition. The present 100-image study does not automatically authorize such a claim.

## Execution gates

First build and independently review a CPU preflight: official members, masks, both mask rasters, native preprocessing identity, task counts, model hashes and image-version alias ledger. Then smoke-test prediction parity, bridge parity, repeatability, CAM generation and independently recomputed localization on a small prespecified sample before full generation. Use the exact established attribution engine; do not rewrite algorithms to make outcomes favorable.

Source/settings and per-task fingerprints must gate checkpoint reuse. Software errors, changed hashes, nonfinite arrays and parity failures block generation. Declared constant maps remain saved audit outcomes. Preserve all source arrays on Drive and include a prespecified array sample plus complete fingerprints in the compact review bundle.

The ongoing six-method HAM 40-image study remains an independent prospective dataset. This design does not replace its cohort or extend its running notebook.
