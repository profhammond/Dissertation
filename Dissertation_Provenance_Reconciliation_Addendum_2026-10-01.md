# Provenance reconciliation addendum — 1 October 2026

This addendum updates Dissertation_Continuation_Provenance_Audit_2026-10-01.md using four newly supplied compact bundles. It supersedes the earlier request to recover these particular predecessor reports. The original manuscript and evidence files remain unchanged.

## CAM reproduction chain now documented

| Stage | Recorded result | Scope |
|---|---|---|
| Initial baseline pairing diagnostic | 23,040 rows; 96 sampled tasks | Diagnostic only; no scientific-validation pass |
| Grad-CAM remediation provenance recovery | 5,760 / 7,680 pairs verified | Existing native arrays reproduced v3 metrics |
| HAM→ISIC baseline recovery | 320 / 320 baseline maps recovered; 1,920 / 1,920 comparisons verified | Original saved model weights; no retraining |
| Internal integration | 7,680 verified CAM comparisons in separate 23,040-row manifest | CAM consolidation; remaining methods pending |

The first recovery left 1,440 pairs with exact model/method/image maps unresolved and 480 pairs for which no native pair reproduced stored metrics. The later transfer recovery supplies the remaining 1,920 comparisons. These totals must not be added to 7,680 again: they are its two contributing subsets.

Independent reconciliation here finds all 5,760 verified initial-recovery map pairs in the integration ledger, and all 1,920 transfer-recovery pairs in that ledger by matching baseline and comparison paths. The subsets do not overlap and together cover all 7,680 integrated CAM pairs. Transfer experiment/image/preprocessing/resolution/method keys also join after case normalization of image IDs. No duplicate task IDs occur in either predecessor report.

The transfer report's maximum absolute errors are Pearson 1.11e-16, SSIM 1.11e-16, and primary EDI 2.22e-16; its configured tolerance is 1e-4. The initial recovery records verification booleans/reasons rather than per-row numerical errors, so those errors cannot be independently summarized from its compact bundle. Both predecessor source identities match the integration configuration: canonical SHA-256 6f4d3d947e06d3a6f4d9673c9da3a1eaa5fafd944b2bb7d2c440a45b52357bf7 and remediation SHA-256 36ab13e5027af405700859923c17149b9e18140443e54b76a274d6057a9f5ab7. These are consistent reported identities; the actual source CSV files were not newly supplied to independently hash here.

The transfer configuration includes four model-file hashes, 40 input-image hashes and a function-source hash. Its generation plan contains 320 entries (four resolutions × two CAM methods × 40 images). The recovered baseline arrays reside in the dedicated transfer-recovery directory. Thus, saying the integration run generated no maps is correct, but extending that statement to the complete recovery chain would be misleading. The recovery chain produced baseline attribution maps using existing models; it did not retrain them. Exact generation code and array hashes are still needed for independent repeatability.

## Image-ID alias requiring preservation

The transfer report uses ISIC_0015232_downsampled; the integration ledger uses ISIC_0015232_DOWNSAMPLED. This causes 48 exact-key mismatches (six preprocessing conditions × four resolutions × two CAM methods), resolved by case normalization; the original map paths agree for all 48. Preserve both source IDs, use a documented canonical-ID field and an alias ledger, and validate one-to-one mapping. Do not remove the downsampled suffix or equate downsampled and original images without image evidence.

## Baseline issues distinguished

The diagnostic reports 11,520 configuration mismatches across Eigen-CAM, IG, Score-CAM and SHAP (2,880 per method), and 5,760 baseline-ID/path inconsistencies across the two CAM methods (2,880 each). These are different problem types in the earlier source snapshot. The CAM recovery/integration supplies resolved array-path evidence for CAMs; do not describe the old CAM path inconsistencies as still unresolved. The four other methods remain pending.

The 96-task diagnostic sampled one row per configuration/method/resolution. It evaluated 2,000 protocol combinations, which are candidate metric calculations rather than 2,000 independent comparisons. Only three sampled tasks had any recorded-metric match and one had an intended-metric match, all Eigen-CAM. Most sampled tasks did not reproduce under tested settings. This does not establish that all other rows are invalid: it motivates recovering the actual generation/comparison protocol rather than guessing resize, normalization or SSIM window settings. Even a match among many tested settings is diagnostic evidence, not proof of the original protocol.

The current remaining-method plan remains 15,360 rows, 11,520 baseline-ID mismatches, 3,744 rows with candidates and 11,616 without candidates. Candidate presence is not numerical reproduction.

## Folder inventory: useful leads, limited coverage

The inventory reports 2,760 scanned directories, 92,159 listed files, 141 identified experiments, 500 inspected schema/configuration records and zero scan errors. It excludes 190 locations, has 17 entry-limited directories and a maximum depth of seven. It explicitly excludes datasets, maps/heatmaps, checkpoints, backups and provenance_inventory. Consequently 141 identified experiments neither validates nor disproves the dissertation's 252-model count. Pending directories = 0 means the bounded traversal finished; it does not make the scan exhaustive.

## Revised next steps

1. Obtain executed original CAM recovery/generation code and per-map hash ledgers if independent repeatability is required. Do not rerun the now-accounted-for 7,680 CAM comparisons by default.
2. Build the remaining-method original-protocol and existing-array audit on CPU, starting with the supplied 15,360-row plan. Identify configuration-correct references and recover actual comparison settings before judging reproduction.
3. Recover the current combined dissertation-mode manifest and external audits, using the folder paths below as leads. Verify contents and versions before selecting authoritative sources.
4. Recover model/classification/pilot evidence and source CSV/code for every dissertation table and figure. Build on the earlier referenced-output register.
5. After evidence locking, update manuscript scope claims, retain recovered/generated-map provenance, document image-ID aliases, restore intended appendices and compile for visual review.

## Selected existing-file leads from the bounded folder inventory

These are inventory records, not files read or validated in this conversation. Filenames may be stale; inspect candidate contents and hashes before using them.


**external_validation_edi_manifest.csv**

- `/content/drive/MyDrive/Dissertation/ExternalValidation_Manifest/external_validation_edi_manifest.csv`

**external_validation_manifest.csv**

- `/content/drive/MyDrive/Dissertation/ExternalValidation_Manifest/external_validation_manifest.csv`

**combined_manifest_integrity**

- `/content/drive/MyDrive/Dissertation/Cross_Domain_EDI_Analysis/exports/combined_manifest_integrity_report.csv`

**paper_analysis_manifest**

- `/content/drive/MyDrive/Dissertation/Cross_Domain_EDI_Analysis/tables/paper_analysis_manifest_edi_validation.csv`
- `/content/drive/MyDrive/Dissertation/Cross_Domain_EDI_Analysis/tables/paper_analysis_manifest_balanced_four_methods.csv`
- `/content/drive/MyDrive/Dissertation/Cross_Domain_EDI_Analysis/tables/paper_analysis_manifest_balanced_six_methods.csv`
- `/content/drive/MyDrive/Dissertation/Cross_Domain_EDI_Analysis/tables/paper_analysis_manifest_bounded_edi.csv`

**analysis_manifest.json**

- `/content/drive/MyDrive/Dissertation/edi_exports/analysis/analysis_manifest.json`
- `/content/drive/MyDrive/Dissertation/edi_exports/manifest/analysis_manifest.json`

**p5_publication_manifest**

- `/content/drive/MyDrive/Dissertation/edi_exports/analysis/p5_publication_manifest.json`
- `/content/drive/MyDrive/Dissertation/edi_exports/analysis/p5_publication_manifest_updated.json`
- `/content/drive/MyDrive/Dissertation/edi_exports/manifest/p5_publication_manifest.json`
- `/content/drive/MyDrive/Dissertation/edi_exports/manifest/p5_publication_manifest_updated.json`

**edi_training_repeatability_provenance**

- `/content/drive/MyDrive/Dissertation/edi_training_repeatability/edi_training_repeatability_provenance_20260912T135647.zip`

**edi_architecture_generalization_model_provenance**

- `/content/drive/MyDrive/Dissertation/edi_architecture_generalization/edi_architecture_generalization_model_provenance.zip`

**table_figure**

- `/content/drive/MyDrive/Dissertation/edi_dissertation_results_table_figure_assembly_v1/final_status.json`
- `/content/drive/MyDrive/Dissertation/edi_dissertation_results_table_figure_assembly_v1_1/final_status.json`
- `/content/drive/MyDrive/Dissertation/edi_dissertation_results_table_figure_assembly_v1/tables/table_export_provenance.csv`
- `/content/drive/MyDrive/Dissertation/edi_dissertation_results_table_figure_assembly_v1/tables/table_claim_authorization_for_assembly.csv`
- `/content/drive/MyDrive/Dissertation/edi_dissertation_results_table_figure_assembly_v1/tables/table_dissertation_section_evidence_map.csv`

**figure_provenance**

- `/content/drive/MyDrive/Dissertation/edi_exports/tables/ictai_camera_ready_gc_gcpp/gc_gcpp_four_column_figure_provenance.csv`

**master_metrics.csv**

- `/content/drive/MyDrive/Dissertation/master_logs/master_metrics.csv`
- `/content/drive/MyDrive/Dissertation/ExternalValidation_CXR/exports/external_validation_master_metrics.csv`
- `/content/drive/MyDrive/Dissertation/ExternalValidation_ChestXray14/exports/external_validation_master_metrics.csv`
- `/content/drive/MyDrive/Dissertation/ExternalValidation_Fundus/exports/external_validation_master_metrics.csv`
- `/content/drive/MyDrive/Dissertation/ExternalValidation_breakhis/exports/external_validation_master_metrics.csv`

## New input archive identities

- edi_ham_to_isic_baseline_map_recovery_v1_compact_bundle (1).zip: `63879635f8c13598e36259c44f39754e0adb83da7a8d99d2a42349e0503ff570`
- edi_dissertation_folder_artifact_map_v1_compact_bundle (3).zip: `e0b7db416497e35e71d99ebd2089bf4c9bf27814d1dc662372f811d3016316ab`
- edi_gradcam_remediation_provenance_recovery_v1_compact_bundle (1).zip: `522b7517864198a4f0d6250a9669725df8128459a9e87ed92bbcfb4c2d982c0e`
- edi_internal_baseline_pairing_map_provenance_audit_v1_compact_bundle (1).zip: `a886bb8a798767c7f064c46783ce282bbb546a509c569ada77d792d58af8d86f`
