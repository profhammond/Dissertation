# Locked-cohort artifact proxy and mask coverage review — 2026-10-04

Bundle SHA-256: 8e883224f3a4638f0b22f4509661aed351c344251de77970f176e55a63314508.

All seven checksum entries verify. The 40 image IDs, labels, image paths and original-image hashes agree with the preflight. Independently checked detector-positive pixel fractions, dimensions, deterministic sorting and 13/13/14 group assignment. No ties span either stratum boundary. Raw detector generation was not independently rerun from pixels in this review.

| Proxy group | Images | Non-melanoma | Melanoma | Detector-positive area range |
|---|---:|---:|---:|---|
| Low | 13 | 9 | 4 | 0.915–3.633% |
| Middle | 13 | 6 | 7 | 4.331–9.837% |
| High | 14 | 5 | 9 | 11.345–35.127% |

This black-hat mask is the preprocessing detector's trigger-area proxy. It can include dark lesion structures, image borders and non-hair features. It is not independent or validated true hair burden, and positive area is not lesion area. Clinical or artifact-removal quality claims are not authorized.

The class mix differs substantially between groups (4/13 melanoma in low, 9/14 in high). Any later burden–EDI analysis must report class composition and account for label-related heterogeneity rather than interpret a pooled burden trend as an isolated hair effect. With 40 images, subgroup findings remain exploratory and image is the sampling unit; seed/method repetitions do not enlarge independent image counts.

No matches for these 40 image IDs were found in the inspected localization-feasibility v2 exports. Six tables were inspected; three had eligible image/mask schemas. This is an inventory-scoped absence, not proof that no masks exist elsewhere. No new map output was read. Therefore this audit does not supply lesion-localization ground truth for the full six-method cohort.

## Next independent work

The artifact strata can be joined by exact image ID after the six-method run finishes. Faithfulness can be measured without lesion masks, whereas lesion localization requires independent masks. Preserve the current 40-image cohort and do not replace images to obtain favorable localization coverage.

For a separate explanation-quality replication, the existing locked 100-image annotated ISIC cohort is a candidate. Evaluate all three preselected baseline seed models on that cohort without selecting a model on those evaluation outcomes. Verify image/mask identity and labels first; use any performance result to describe applicability, not to choose the strongest seed retrospectively. This inference-only audit can proceed independently of the ongoing attribution run.
