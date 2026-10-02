# Dissertation continuation and provenance audit — 1 October 2026

## Authoritative inputs and limits

This audit reads HAMMOND_DISSERTATION (10).zip and edi_internal_attribution_provenance_integration_v1_compact_bundle(1).zip as supplied. Current source files take precedence over remembered conversation details. No original manuscript, models, arrays, or canonical tables were changed. No experiments were rerun. The compact bundle supplies CSV records and status/configuration JSON, not numerical map arrays, model weights, generation notebooks, or external-domain evidence. Therefore this local audit independently checks manifest structure and formula consistency; it cannot independently repeat the recorded map-level reproduction.

The dissertation's current main.tex specifies March 2027 graduation and Department of Computer Science. These differ from older conversation context and should be confirmed editorially rather than silently changed.

## Recovered status

The run completed at 2026-10-01T19:24:43.353951+00:00. Its validation scope is explicitly CAM provenance consolidation and remaining-method inventory only. Its status authorizes CAM provenance integration, but does not authorize remaining-method numerical reproduction or full-corpus integration. It reports unchanged canonical metrics and original sources, no retraining, and no regenerated maps in this run.

| Layer | Evidence available now | Unresolved work |
|---|---|---|
| Internal structure | 23,040 rows; four configurations; six methods; four resolutions | Confirm map-level pairing for remaining methods |
| Grad-CAM / Grad-CAM++ | 7,680 records marked provenance verified; matching path ledger | Recover predecessor numerical-reproduction reports and map hashes to independently substantiate flags |
| Eigen-CAM / IG / Score-CAM / SHAP | 15,360 records retained with provenance pending | Recover original protocols and configuration-correct pairs; reproduce stored metrics |
| Expanded corpus | Dissertation reports 51,840 comparisons and 252 models | Obtain combined manifest, external source records, model ledger, and full integration audit |
| Classification and later pilots | Results and specifications described in manuscript | Obtain their prediction/cohort/model and pilot evidence bundles |
| Rendered figures | PNG files present | Obtain plotting data, code, selection records, map-level provenance and hashes |

## Independent checks on the compact bundle

- Internal manifest: 23,040 rows and 104 columns.
- No duplicates on experiment_id, image_id, preprocess, resolution, attribution_method in the manifest, verified-CAM ledger, or remaining-method plan.
- Each configuration/method has 960 observations; each method has 3,840 observations.
- The two CAM methods are marked verified for all 7,680 records. The other four methods are marked unverified for all 15,360 records.
- No missing Pearson, SSIM, or primary-EDI values. Maximum error recalculating primary EDI from stored Pearson and SSIM is 4.44e-16. This verifies arithmetic, not the source measurements.
- Primary EDI is the unbounded-with-respect-to-[0,1] formulation: ((1-(Pearson+1)/2)+(1-SSIM))/2, theoretically [0,1.5]. The manuscript correctly describes this range. Do not substitute a bounded-EDI manifest without a documented formulation change.
- The Chapter 4 attribution-method summary agrees with all six per-method means to its six displayed decimals. No conclusion about correct map pairing follows from that agreement.

| Remaining method | Comparisons | Baseline-ID mismatches | Rows with candidate | Rows without candidate |
|---|---:|---:|---:|---:|
| Eigen-CAM | 3,840 | 2,880 | 936 | 2,904 |
| Integrated Gradients | 3,840 | 2,880 | 936 | 2,904 |
| Score-CAM | 3,840 | 2,880 | 936 | 2,904 |
| SHAP | 3,840 | 2,880 | 936 | 2,904 |
| Total | 15,360 | 11,520 | 3,744 | 11,616 |

Candidate counts describe rows, not unique files. There are 3,276 rows with one candidate and 468 with two. Candidate presence does not establish intended model, target, normalization, method settings, or numerical reproduction. A mismatched baseline ID is a provenance problem requiring investigation; this inventory alone does not prove the stored similarity was computed using the wrong array.

## Prioritized continuation plan

1. **Recover predecessor evidence before new computation.** Obtain the Grad-CAM remediation provenance-recovery bundle, HAM-to-ISIC baseline-recovery bundle, and the executed integration notebook. Verify source SHA-256 identities against run_config.json and recover numerical-reproduction tolerances, per-row errors, constant-map handling and source map hashes. Preserve the verified 7,680-row subset.
2. **Audit remaining-method protocols on CPU.** Start with the supplied recovery-plan CSV. Locate original generation notebooks and model metadata for each method and configuration. Resolve the 468 ambiguous candidate rows using protocol/model evidence. Record target class or output, layer, normalization, resize/interpolation, IG baseline/steps, Score-CAM masking/scaling, Eigen-CAM decomposition, SHAP explainer/background/sample/seed settings, library versions and constant/nonfinite policies as applicable. Do not infer these from filenames.
3. **Reproduce existing pairs before regeneration.** For usable arrays, validate shape, identity, finite values and spatial variation, then reproduce Pearson, SSIM and primary EDI with documented tolerances. Keep original recorded pairs and intended configuration-correct pairs separately. If correcting pairing changes numbers, create a versioned corrected metrics manifest; preserve canonical values and describe the change. Regeneration becomes a separate decision only after recovery fails and the exact implementation/model/input can be established.
4. **Audit the expanded cohort independently.** Obtain the 51,840-row dissertation-mode combined manifest and its integration audit. Check nine configurations, 1,296 cells and 40 unique images per cell, duplicates, formulation and source hashes. Audit external map/model provenance separately. Reconcile the eight-configuration manuscript cohort with the nine-configuration dissertation cohort; do not interchange their bootstrap summaries.
5. **Audit classification and pilot evidence.** Obtain model-level metrics and predictions, split identities, class counts, balancing/class-weight policy, thresholds and checkpoint metadata. Independently derive model counts rather than infer them from design alone. Recover separate fixed-model, training-repeatability, localization/faithfulness and other pilot bundles already described in Chapters 3–6. Keep pilot rows outside the main corpus and qualify completed claims until evidence is available.
6. **Lock output lineage and regenerate affected outputs.** Each empirical table/figure needs source manifest hash, row filter/cohort, statistic, uncertainty procedure, generating notebook/script hash, output hash and validation result. Qualitative figures additionally need selected comparison keys, numeric map/image hashes, percentile-selection rule, original map dimensions and display normalization. Recalculate complementary map metrics if corrected pairs change; do not leave legacy metrics alongside newly corrected EDI without explicit lineage.
7. **Refine the dissertation against locked evidence.** Reconcile abstract, Chapters 3–7 and appendices with verified scope. Clearly distinguish inventory, formula consistency, array-level reproduction and independent replication. Review broad completed/audited/full-corpus assertions after evidence recovery. Restore appendices only if intended; they are currently disabled. Confirm training and preprocessing settings from original task-specific notebooks, then perform a full LaTeX compile and visual review.

## Concrete manuscript findings

- main.tex comments out \appendix and every appendix include. Appendix files exist but are not built by the current main document.
- Chapter 5 asserts that controls established an audited 51,840-record cohort; the attached latest audit supports only internal CAM consolidation and inventory. Earlier full-corpus evidence may exist, but is not included here. This is an evidence gap, not proof those results are false.
- Abstract, methodology, conclusion and Appendix D report 252 models / 51,840 comparisons. Validate against a deduplicated model ledger and the actual combined manifest.
- Appendix D currently offers only short introductory/summary text; detailed settings remain in tables and the separate appendix_q.tex, which is not included by main.tex. Decide where those reproducibility details belong.
- tbl_appD_training_configuration.tex states single-sigmoid output, binary cross-entropy, batch size 32, seed 42 and specific epoch/learning-rate settings. The supplied compact bundle does not substantiate those settings. Original notebooks/checkpoints are required; do not import settings from later pilots.
- Chapter 4 contains two attribution galleries: ISIC_0031745 and the P10/P50/P90 CAM examples. The latter caption correctly states metrics were measured at original map dimensions. Obtain figure-specific ledgers for both; visual similarity and PNG filenames cannot establish provenance.
- Manuscript already distinguishes paired independently trained pipelines from preprocessing-only causal effects and stability from clinical correctness. Preserve this qualification.
- Chapter 3 describes additional completed analyses (e.g., 2,160 training-repeatability comparisons and a fixed-model lesion-localization study). Their supporting data are absent from these attachments and should be recovered rather than rerun by default.

## Evidence to bring into this conversation

Priority recovery: executed integration notebook; edi_gradcam_remediation_provenance_recovery_v1_compact_bundle.zip; edi_ham_to_isic_baseline_map_recovery_v1_compact_bundle.zip; original attribution-generation notebooks for Eigen-CAM, IG, Score-CAM and SHAP. Then bring the current combined dissertation manifest/integrity report and NB11, P5/P6 builder and source CSV exports, table/figure generation code and underlying numeric exports, model ledger and classification/pilot audit bundles. Known earlier filenames are leads, not presumed current authoritative versions. Large map archives need not be uploaded initially: a CPU Colab audit can inspect them in Drive and export compact results and hashes.

## Continuation instructions

Use these two attachments and subsequent validated evidence as the starting state. Do not rerun completed experiments by default. Do not merge the provenance-corrected internal manifest into the canonical/full corpus solely because validation_passed is true. Respect the stated validation scope. Keep every original source and metric unchanged while constructing explicitly versioned corrective evidence. The next notebook should implement remaining-method protocol and existing-array reproduction, beginning with small verified pilot cells and exporting per-row evidence plus explicit scope-specific status flags.

## Referenced artifact register

The following register captures uncommented table and image references in the main document and seven chapters. Presence only establishes that the file is packaged, not numerical provenance or visual correctness. Every empirical output needs its generation evidence; conceptual diagrams need specification review. Appendices are omitted from active references because their main.tex includes are commented out.

| Source | Type | Artifact | Packaged | SHA-256 (first 16) |
|---|---|---|---|---|
| 02_literature_review.tex | includegraphics | figures/fig_CH02_taxonomy_hair_removal_methods.png | Yes | d48abfe6808bf4d1 |
| 02_literature_review.tex | includegraphics | figures/fig_CH02_hair_removal_evolution.png | Yes | be126dad6388d97c |
| 02_literature_review.tex | input | tables/tbl_CH02_similarity_summary | Yes | 9c3357a4e13529b1 |
| 03_methodology.tex | includegraphics | figures/fig_CH03_overall_methodology_architecture.png | Yes | 524bbd4c46ca4b15 |
| 03_methodology.tex | includegraphics | figures/fig_CH03_matched_domain_learning_framework.png | Yes | a2490631dac30c70 |
| 03_methodology.tex | includegraphics | figures/fig_CH03_experimental_matrix_overview.png | Yes | f1ad62170b730e3a |
| 03_methodology.tex | input | tables/tbl_CH03_experimental_matrix_summary | Yes | 94b79882fe52649d |
| 03_methodology.tex | includegraphics | figures/fig_CH03_Attribution_generation_and_evaluation_pipeline.png | Yes | 8c0709e25cca5e23 |
| 03_methodology.tex | input | tables/tbl_CH03_attribution_methods | Yes | 57ce32574ddae72b |
| 03_methodology.tex | input | tables/tbl_CH03_attribution_manifest_schema | Yes | 708e48411eba059d |
| 03_methodology.tex | input | tables/tbl_CH03_evaluation_metrics | Yes | bedd7ca9511bbd5d |
| 03_methodology.tex | input | tables/tbl_CH03_statistical_validation_summary | Yes | 2a24b45eeb645ac7 |
| 03_methodology.tex | includegraphics | figures/fig_CH03_reproducibility_audit_trail.png | Yes | 2f1d934cc00a84c0 |
| 04_results.tex | includegraphics | figures/Fig_CH04_Experimental_evaluation_roadmap.png | Yes | 7a5dc3ad32072076 |
| 04_results.tex | includegraphics | figures/fig_CH04_overall_classification_performance_by_preprocessing.png | Yes | 5f46486d4f8a944e |
| 04_results.tex | input | tables/tbl_CH04_overall_classification_performance | Yes | b3e7792a3d038a45 |
| 04_results.tex | includegraphics | figures/fig_CH04_dataset_specific_roc_auc_by_preprocessing.png | Yes | ee4634c760c36611 |
| 04_results.tex | input | tables/tbl_CH04_dataset_specific_performance_summary | Yes | d587e535e79824d4 |
| 04_results.tex | input | tables/tbl_appA_dataset_specific_classification_performance | Yes | ccb18909170a39a2 |
| 04_results.tex | includegraphics | figures/fig_CH04_resolution_specific_roc_auc_trends.png | Yes | 3fe9a6f5eb3bbe00 |
| 04_results.tex | input | tables/tbl_CH04_resolution_performance_summary | Yes | 6b9efa4d1decc640 |
| 04_results.tex | input | tables/tbl_appA_resolution_specific_classification_performance | Yes | 653b7d33d0da4872 |
| 04_results.tex | includegraphics | figures/fig_CH04_classification_performance_metric_heatmap.png | Yes | b9dcd9228fd7d556 |
| 04_results.tex | input | tables/tbl_CH04_classification_performance_ranking | Yes | 26dc0c1b891b6a01 |
| 04_results.tex | includegraphics | figures/fig_CH04_ISIC_0031745_gradcam_sorted_edi_comparison.png | Yes | fa3a9cffebeef49c |
| 04_results.tex | includegraphics | figures/fig_appendix_c_gc_gcpp_verified_examples_four_column.png | Yes | faab3dc03f7f2dc9 |
| 04_results.tex | input | tables/tbl_CH04_attribution_similarity_summary | Yes | 40ccd0695bd432ca |
| 04_results.tex | includegraphics | figures/fig_CH04_attribution_similarity_metric_heatmap.png | Yes | 170df31719f31648 |
| 04_results.tex | includegraphics | figures/fig_CH04_similarity_metric_correlation_matrix.png | Yes | df949778f21a4932 |
| 04_results.tex | includegraphics | figures/fig_CH04_attribution_method_mean_edi.png | Yes | 83148e01e75bc303 |
| 04_results.tex | input | tables/tbl_CH04_attribution_method_summary | Yes | 7af3e858426759e1 |
| 04_results.tex | includegraphics | figures/fig_CH04_mean_edi_by_preprocessing_with_ci.png | Yes | 4a985d5b54101e53 |
| 04_results.tex | input | tables/tbl_CH04_edi_summary_by_preprocessing | Yes | dbfb24f29edbd527 |
| 04_results.tex | includegraphics | figures/fig_CH04_mean_edi_by_resolution.png | Yes | f2402e89cff82e77 |
| 04_results.tex | input | tables/tbl_CH04_edi_summary_by_resolution | Yes | 6e0a9d0eab98edc9 |
| 04_results.tex | input | tables/tbl_CH04_edi_summary_by_dataset | Yes | 3abce8173e7d4135 |
| 04_results.tex | input | tables/tbl_CH04_edi_component_validation | Yes | fe1a82bd5bbbe144 |
| 04_results.tex | input | tables/tbl_CH04_edi_component_pair_correlation | Yes | 7ee199f550ed7cc4 |
| 04_results.tex | input | tables/tbl_CH04_metric_validation_expected_vs_observed | Yes | e041220228d65c39 |
| 04_results.tex | input | tables/tbl_CH04_metric_validation_rank_correlation | Yes | 387d8c2e3a6ef982 |
| 04_results.tex | input | tables/tbl_CH04_independent_metric_validation | Yes | bcba8cd0105592fa |
| 04_results.tex | input | tables/tbl_CH04_independent_validation_summary | Yes | 16ce9b7c7432275a |
| 04_results.tex | input | tables/tbl_CH04_cross_attribution_rank_agreement | Yes | a7936d399ff7c168 |
| 04_results.tex | input | tables/tbl_CH04_weight_sensitivity_by_preprocessing | Yes | bd4bcef5d6d7b2ae |
| 04_results.tex | input | tables/tbl_CH04_weight_sensitivity_rank_agreement | Yes | 40f0aaee62a9f5c9 |
| 04_results.tex | includegraphics | figures/fig_CH04_performance_stability_tradeoff_by_preprocessing.png | Yes | 78c6774229581e2b |
| 04_results.tex | input | tables/tbl_CH04_performance_stability_correlation | Yes | 8ef84fca08820374 |
| 04_results.tex | includegraphics | figures/fig_CH04_performance_stability_quadrants.png | Yes | c8143a4f939e151d |
| 04_results.tex | input | tables/tbl_CH04_research_question_summary | Yes | d38e9bc39e6a207b |
| 05_EDI.tex | input | tables/tbl_appA_experiment_manifest_summary | Yes | faa9f32f84d273b9 |
| 05_EDI.tex | input | tables/tbl_CH05_analytical_cohorts | Yes | a58aedbc2a72ff88 |
| 05_EDI.tex | input | tables/tbl_appB_edi_distribution_summary | Yes | 74462213ba1fadd7 |
| 05_EDI.tex | input | tables/tbl_CH05_cross_configuration_edi_summary | Yes | cc5bd561a03ca926 |
| 05_EDI.tex | input | tables/tbl_CH05_edi_by_attribution_method | Yes | 73440aaedeb29d1b |
| 05_EDI.tex | includegraphics | figures/fig_CH05_edi_configuration_attribution.png | Yes | 6bb8da78e6c66fc8 |
| 05_EDI.tex | input | tables/tbl_CH05_edi_by_preprocessing | Yes | 2b696687e445ef3c |
| 05_EDI.tex | input | tables/tbl_CH05_edi_by_resolution | Yes | 6f9db3aa1636fb3c |
| 05_EDI.tex | includegraphics | figures/fig_CH05_domain_euclidean_distance_heatmap_updated.png | Yes | b8015b02d2752c30 |
| 05_EDI.tex | includegraphics | figures/fig_CH05_pca_configuration_structure.png | Yes | 00eed86837efbf45 |
| 05_EDI.tex | input | tables/tbl_CH05_pca_explained_variance | Yes | 081f60cbd81aa89a |
| 05_EDI.tex | input | tables/tbl_CH05_lodo_pca_summary | Yes | e5e1db19498f959f |
| 05_EDI.tex | input | tables/tbl_CH05_cross_attribution_rank_agreement | Yes | 523f1a43f6482dec |
| 05_EDI.tex | input | tables/tbl_CH05_configuration_weight_sensitivity | Yes | d4cb1140787d8be0 |
| 05_EDI.tex | input | tables/tbl_CH05_preprocessing_weight_sensitivity | Yes | 45668f0256261bf4 |
| 05_EDI.tex | input | tables/tbl_CH05_alternative_edi_formulation_summary | Yes | 7573f88589684cbe |
| 05_EDI.tex | input | tables/tbl_CH05_preprocessing_ranks_by_formulation | Yes | 3ebc0e7a5ef6e602 |
| 05_EDI.tex | input | tables/tbl_CH05_negative_ssim_sensitivity | Yes | 969c8ec08887e572 |
| 05_EDI.tex | input | tables/tbl_CH05_bootstrap_preprocessing_rank_stability | Yes | 069fc8e42062ea7e |

## Input archive SHA-256

- HAMMOND_DISSERTATION (10).zip: `03f6fc9eda2603aaa272555d2bf4fa4450692c8e409146b585e84f78a3726d6a`
- edi_internal_attribution_provenance_integration_v1_compact_bundle(1).zip: `4f967ce3365eb863fc931ff7b7d521c3a1c3ce4dbfbb546e4fdb2645833f86e7`
