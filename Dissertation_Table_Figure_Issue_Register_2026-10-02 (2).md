# Dissertation table and figure provenance register

Updated October 3, 2026, 12:48 America/New_York. This current status supersedes the original October 2 snapshot retained at the end. The filename is retained for continuity. Numerical reproduction, exact artifact identity, interpretation, and original model/map-generation lineage are separate findings; none implies all others.

## Current authoritative source and scope

- Dissertation: `HAMMOND_DISSERTATION (11).zip`; SHA-256: `58830ae4c517f31e63c955e82a9d31a3a9ffe7074c0cdbbdf0ea25d1f80a3e29`.
- Dissertation analysis manifest: `/content/drive/MyDrive/Dissertation/Cross_Domain_EDI_Analysis/tables/paper_analysis_manifest_balanced_six_methods.csv`.
- Manifest: 51,840 rows, nine configurations, six attribution methods, six preprocessing transformations, four resolutions, 40 images/configuration, 144 rows/configuration/image.
- Manifest SHA-256: `a1c5e55f7ab4935076dad87c77ad45f0f767978cb1583631a279326d12b5cd7c`. Exact source bytes match the earlier tables ZIP and the CPU Colab reproduction run.
- Latest accepted source includes the manuscript-output remediation. Copy/paste changes made after this upload remain unconfirmed until a newer source is supplied.

## Chapter 5 checks completed October 3

| Artifact / claim | Current status | Evidence and limits |
|---|---|---|
| Overall EDI bootstrap | Numerically reproduced | NB11 cell 84; seed 20260719; 2,000 draws. New CSV is byte-identical to `table_overall_primary_edi_bootstrap.csv`. Mean 0.362025483865002; SE 0.0019663515063287618; CI 0.35818228952597786–0.3658682559238119. |
| Older Chapter 5 draw export | Superseded for dissertation use | User identified manuscript-specific origin. Its summary itself describes nine configurations and the same observed mean; differing draws do not prove a smaller cohort or damaged data. Preserve it; do not claim an exact historical generator/rename reconstruction. |
| Manuscript-output remediation | Confirmed applied in current source | Chapter 3 manuscript-cohort convergence evidence removed; Chapter 5 manuscript-derived SSIM-window subsection removed; abstract scope claim removed; seed and interval updated; preprocessing-bootstrap table and prose updated. |
| Preprocessing bootstrap ranks | Rebuilt and applied | Same image draws across all transformations; seed 20260719. Overall means agree with NB11 within 1e-12. Telea mean rank 1.2225 / probability first 0.7775; Navier–Stokes 1.7775 / 0.2225; both top two throughout. |
| Negative-SSIM sensitivity | Numerically reproduced | 6,875/51,840 = 13.26196%. Full/clipped/normalized mean EDI 0.362025/0.349678/0.238537. Preprocessing ranks identical; configuration displacement at most one. Current table matches displayed precision. |
| Alternative-formulation tables and ranks | Numerically reproduced | Recalculate from components; all preprocessing ranks identical. Global/geometric swap HAM and COVIDx only (rho 0.983333, tau 0.944444). Current LaTeX summary matches. |
| Stored alternative columns in frozen manifest | Inconsistent; separate derived copy prepared | Five columns differ from documented component-based calculations. Primary EDI matches within rounding error. Original preserved. Cause is not established or attributed to manuscript code. Use `dissertation_manifest_recalculated_alternative_formulations_v1.csv` for future alternative-formulation aggregation. |
| Component-weight sensitivity | Numerically reproduced | 21 weights and 189 configuration profiles reproduce within 1.4e-16. First tested exchange is w=0.65, HAM/COVIDx. Internal 23,040-row preprocessing ranks and rho 0.943 / tau 0.867 reproduce. |
| PCA | Numerically reproduced | 9×12 component matrix, standardized features, scores/loadings aligned for arbitrary signs. Errors below 3e-15. PC1 59.518%; PC2 15.199%; cumulative 74.717%. |
| Leave-one-configuration-out PCA | Numerically reproduced | All nine recomputations reproduce within 6e-16. PC1 variance 0.491724–0.646812; leading loading cosine 0.973383–0.999641. Exploratory, not population-domain validation. |
| Configuration-distance matrix | Numerically reproduced | All 81 cells reproduce within 1e-16 from six preprocessing means. COVIDx/NIH closest (0.035895); combined/APTOS most separated (0.366816). |
| SIPaKMeD nearest-neighbor prose | Correction supplied; application unconfirmed | Uploaded source incorrectly says HAM→ISIC closest. Export and recalculation agree: BreakHis 0.085824; then HAM→ISIC 0.102263 and HAM 0.127957. |
| Configuration-by-attribution figure source | Numerically reproduced | NB11 cell 77; seed 20260718; 54 groups × 2,000 = 108,000 draws, errors below 1e-16. All 54 means/108 bounds reproduce. Original PNG visually displays nine configurations/six methods. Rendering subsequently regenerated from verified data/code and delivered; replacement is user-reported, pending confirmation in newer dissertation source. |

## Additional completed audits and figure status

| Artifact / claim | Current status | Evidence and limits |
|---|---|---|
| Chapter 5 figure rendering | Reproduced and replacement package delivered | Original NB11 plotting cells recovered; attribution, distance and PCA renders generated from verified inputs. PCA label layout refined without numerical change. User reports replacing attribution and PCA PNGs and retaining the verified original distance heatmap. New source ZIP/hash verification remains open. |
| Model–input factorial | Numerical audit passed | 2,400 records; 40 images; 60 cells × 40; no duplicate keys. Twelve displayed means match. All 40 bootstrap contrasts, 60 seed results and 20 seed-heterogeneity rows reproduce within 9.72e-17. 5,000 draws; seed 20260912. DullRazor Grad-CAM contrast 0.101150, CI [0.046053, 0.157561]; Telea 0.112585, CI [0.058838, 0.164418]. Prior total alignment checked against reconciliation export, not independently recovered earlier source. |
| Matched initialization | Numerical and saved completion-record audit passed | 2,160 records; 27 pair identifiers reconstructed; six displayed means, four differences and two ratios match. 720 diagnostics; fallback 44 Grad-CAM + 24 Grad-CAM++. Nine uploaded DONE records cover all conditions/seeds once: one nonempty matching initialization digest per seed, three different digests across seeds. Initial weights themselves not rehashed. |
| Architecture pilot | Numerical, diagnostics and saved model/prediction audit passed | 1,680 comparisons (720 primary + 960 cross-architecture); 21 planned pairs; twelve completion records; 960 diagnostics. Six secondary tables reproduce exactly numerically including bootstrap results (5,000 draws, seed 20260916). 43 fallback maps affect 60 primary comparisons; exclusion changes no preprocessing rank. Saved prediction metrics agree within 1.18e-10. Three empty fine-tuning histories confirmed and already disclosed. |
| ISIC fixed-model associations | Complete-cohort inference reproduced | 900 comparisons / 100 images. All seven pooled estimates, intervals and centered-bootstrap p-values reproduce; 2,000 draws, cohort seed 20260913. BH q-values reproduce from all 154 exported p-values. The other 21 sensitivity cohorts' bootstrap p-values were not regenerated. Deletion rho 0.018122 and soft-IoU rho -0.026926 match Chapter 5. |
| PH2 auxiliary localization | All association inference reproduced | 1,800 comparisons / 200 images. Sixteen pooled/method estimates, intervals, sign probabilities and q-values reproduce; 2,000 draws, seed 20260922. Pooled soft-IoU rho 0.105250, CI [0.020439, 0.181300], q 0.016; method-specific values match. Auxiliary cohort; no clinical-validation claim. |
| Deletion perturbation protocols | Numerical sensitivity audit passed | All nine protocols reproduce estimates, intervals, sign probabilities and q-values; 2,000 draws, seed 20260923. Rho rounds to [-0.030, 0.020]; every interval includes zero. |
| Frozen-model ISIC ROC-AUC | Reproduced from saved predictions | Original evaluation file has 1,200 records. Baseline labels/probabilities agree across methods; collapse to 100 unique images (50 melanoma, 50 non-melanoma). ROC-AUC 0.4164 correctly rounds to 0.416. No fresh inference performed. |
| Deterministic negative controls | Saved-data audit passed | 3,600 unique tasks; all 18 mean-advantage bootstrap rows reproduce within 9.72e-17; 2,000 draws, seed 20260922. Real metrics match original evaluation exactly. Mask derangement reproduces without self-pairs. Mixed results support Chapter 5 wording; uniformly superior explanations are not established. |
| Bootstrap testing definitions | Clarification prepared; application unconfirmed | ISIC association audit uses centered-bootstrap null approximation. PH2, negative controls and protocol audit use bootstrap sign probabilities; some columns misleadingly say centered_bootstrap_p. BH families differ (154, 16, 18, nine). Optional methods clarification is in faithfulness audit README; do not silently pool families or treat testing procedures as identical. |
| Protocol prediction parity | Practical agreement recorded; exact agreement failed | Source parity audit: 400 inputs, max probability difference 0.0121685, mean 0.00140077; 399/400 class agreement. One disagreement near threshold. Source passes specified practical tolerances; exact tolerance 0.0001 fails. We inspected the saved parity evidence; fresh inference was not reproduced. Retain this qualification in final reproducibility review. |

All these findings concern saved evidence and downstream computations. They do not certify original model training, attribution generation, raw pixel-to-quality computations, or universal metric validity. Pilot records remain separate from the principal manifest.

## Earlier Chapter 4 findings retained

These findings were completed earlier in this conversation; this register update does not independently rerun those audits.

- CH04 authoritative builder reproduced preprocessing and resolution image-clustered bootstrap intervals, 96-model performance–stability correlations, and 13 aggregation/rank/complementary-metric exports. Dataset-summary export has no confidence intervals; prose correction was supplied earlier.
- Exact exported identities were found for four classification figures, similarity heatmap/matrix, attribution mean, preprocessing/resolution plots and renamed quadrant figure. Original snapshot's blanket assertion that no figures match is obsolete.
- Tradeoff coordinates reproduce from model-level aggregates. Separately supplied image was resized; exact original rendering remains unproven.
- Representative Grad-CAM figure recovery: six pairs verified against corrected metric records and map hashes; new recovery figure prepared. This verifies paired metric data, not original attribution generation or historical rendering. Current source figure use should remain tied to its recovery ledger.
- Internal Grad-CAM/Grad-CAM++ metric reproduction covers 7,680 comparisons. Configuration-specific baseline pairing and numerical reproduction remain unresolved for the other four methods' 15,360 internal comparisons.
- Complementary-metric aggregation does not by itself reproduce each metric from map arrays or establish independent clinical validation. Expected-order tests are exploratory; their rationale is separate evidence.

## Remaining tasks in order

1. **Close four-method baseline provenance.** Eigen-CAM, Score-CAM, IG and SHAP cover 15,360 internal comparisons whose configuration-correct baseline pairing/numerical map reproduction remains unresolved. Candidate files exist under `edi_exports/heatmaps/baseline_by_method/{eigencam,scorecam,ig,shap}`. Candidate existence is not verification. Inspect exact method/domain/resolution/model/input metadata and pair keys before accepting a baseline or running metric reproduction. Preserve original artifacts; write audit results separately.
2. **Confirm final manuscript source.** Obtain the next dissertation ZIP to verify the SIPaKMeD nearest-neighbor correction and user-reported attribution/PCA PNG replacements. Retained distance heatmap values have been verified. New rendering hashes need not equal an older rendering; the chosen version must have documented input/code lineage.
3. **Review reproducibility qualifications and active appendices.** Preserve the three architecture logging gaps, distinctions among bootstrap testing procedures/families, practical versus exact probability parity, and the limits of saved-record verification. Inspect appendix representative-map/percentile selection provenance; earlier historical entries are not current proof of closure.
4. **Check any claims not covered by completed audit scopes.** Examples: non-pooled ISIC sensitivity bootstrap calculations, original pilot model/map generation and raw map-to-quality metrics, earlier fixed-model source reconciliation. Do not expand “passed” beyond the documented scope. Prioritize only claims actually used in the current dissertation.
5. **Compile and review final source/PDF.** Confirm labels, captions, table values, cross-references, bibliography and accepted copy/paste changes. No fresh full Overleaf compile has been checked in this session.
6. **Assemble dissertation GitHub repository and continuity handoff.** Include immutable source hashes, analysis scripts, run instructions, this register, artifact mappings and unresolved items. A repository starter exists; publication of a dissertation repository is not completed. Keep it distinct from the separate PseudoClean manuscript repository.

Next concrete task: recover the latest four-method baseline inventory/provenance notebook and results, inspect its unresolved rows, then prepare only the audit needed to close those gaps. Do not regenerate maps or retrain models to resolve a filename/path or pairing problem.

## Durable evidence packages

- `nb11_bootstrap_reproduction_20261003T140336_797826Z.zip`: completed CPU Colab run.
- `CH05_Manuscript_Output_Remediation_v1.zip`: guarded patch/copy-paste revisions, joint preprocessing bootstrap outputs and validation.
- `CH05_Formulation_Provenance_Audit_v1.zip`: recalculated formulation summaries/ranks, source discrepancy ledger, separate derived manifest and hashes.
- `ch04_verified_gradcam_figure_recovery_v1_20261003T005726Z-20261003T010158Z-1-001.zip`: representative-map recovery evidence.
- `CH05_Figure_Rendering_Provenance_v1.zip`: verified plotting code, source data/hashes, regenerated figures and replacement PNGs.
- `CH05_Factorial_Provenance_Audit_v1.zip`: factorial means, bootstrap and seed-summary reproduction.
- `CH05_Matched_Initialization_Provenance_Audit_v2.zip`: supersedes v1; adds nine completion records and digest checks.
- `CH05_Architecture_Provenance_Audit_v1.zip`: pilot/secondary analysis, prediction and logging checks.
- `CH05_Faithfulness_Localization_Provenance_Audit_v1.zip`: ISIC pooled, PH2 and protocol sensitivity inference; methods clarification.
- `CH05_Fixed_Model_Performance_Negative_Control_Audit_v1.zip`: saved-prediction ROC-AUC and negative-control reproduction.

Preserve original canonical data and model/map artifacts. No retraining or broad attribution regeneration is authorized or required by these aggregation checks. Results should not be described as clinical correctness, clinical thresholds, or independent training reproducibility.

## Historical October 2 snapshot — superseded

The snapshot below records the starting audit state. Its open/closed labels and figure identity claims are not the current status; use the sections above.

---

# Dissertation table and figure issue register

Audit date: October 2, 2026. Scope: uploaded dissertation package, Chapter 4 notebook and exports, P5 analysis exports, and construct-validation v5 bundle. Filenames identify artifacts more reliably than draft-dependent table/figure numbers. Unresolved provenance is not proof of an incorrect value.

## Priority 1: uncertainty and statistical inference

| Dissertation artifact | Issue | Required resolution |
|---|---|---|
| `tbl_CH04_edi_summary_by_preprocessing.tex` | Means match the confirmed internal source. Dissertation confidence intervals differ from the uploaded Chapter 4 export; Navier–Stokes 0.3461–0.3652 versus 0.3457–0.3653. Export uses individual-row bootstrap despite repeated images/models. | Identify final generating code, seed, row order, and resampling unit; justify dependence handling. |
| `tbl_CH04_edi_summary_by_resolution.tex` | Export intervals reproduce an individual-row bootstrap. Final dissertation generation remains unlinked. | Trace final intervals and review resampling unit. |
| `tbl_CH04_edi_summary_by_dataset.tex` | Same uncertainty/provenance issue as above. | Trace final intervals and review resampling unit. |
| `fig_CH04_mean_edi_by_preprocessing_with_ci.png` | Depends on the unresolved confidence-interval version; no exact byte match to uploaded export. | Link figure to verified final summary and generation code. |
| `fig_CH04_mean_edi_by_resolution.png` | Dissertation caption describes confidence intervals; uploaded export generation code produces a mean-only line plot. | Verify final plot data and error bars against final table. |
| `tbl_CH04_performance_stability_correlation.tex` | Uploaded export computes correlations and p-values using 23,040 rows; model-level classification metrics repeat across attribution/image rows. | Inspect final table; use an appropriate model-level or dependence-aware analysis. |

## Priority 2: stale analysis and unresolved attribution provenance

| Dissertation artifact | Issue | Required resolution |
|---|---|---|
| `tbl_CH04_weight_sensitivity_by_preprocessing.tex` | Uploaded P5 source excludes 9,848 rows because existing drift fields are missing and uses older CAM values. Its exports reproduce a 13,192-row subset. Dissertation prose instead reports full-cohort means, so the final dissertation table must not be presumed to derive from the stale export. | Identify final generating code/input; compare all weights and ranks with complete confirmed internal metrics. |
| `tbl_CH04_weight_sensitivity_rank_agreement.tex` | Same stale P5 input issue; final dissertation lineage unresolved. | Reconcile with the final weighting table and its cohort. |
| `tbl_CH04_attribution_method_summary.tex` | Mean EDI values match confirmed internal metrics, but configuration-correct baseline provenance remains unresolved for Eigen-CAM, Score-CAM, IG, SHAP. | Retain method-specific verification status; close map/model/input/pairing provenance. |
| `fig_CH04_attribution_method_mean_edi.png` | Shares method provenance issue; final caption describes means and IQR, unlike the legacy export. | Trace plotting dataframe and quartiles; verify method provenance. |
| `tbl_CH04_attribution_similarity_summary.tex` | Complementary similarity metrics require source-map linkage, including checking whether CAM metrics were recomputed after remediation. | Verify each metric against the same map pair used for primary EDI. |
| `fig_CH04_attribution_similarity_metric_heatmap.png` | Depends on preceding similarity table; generating artifact not in supplied Chapter 4 export set. | Link to final dataframe and plotting code. |
| `fig_CH04_similarity_metric_correlation_matrix.png` | Same-map metric association does not establish independent validation; final generation unlinked. | Trace cohort, metric definitions and correlation computation. |
| `tbl_CH04_independent_metric_validation.tex` and `tbl_CH04_independent_validation_summary.tex` | Same-pair complementary metrics are not independent clinical/faithfulness evidence; post-remediation linkage remains unverified. | Audit metric inputs and clarify interpretation. |
| `tbl_CH04_cross_attribution_rank_agreement.tex` | Final generation and rank estimand unresolved; uploaded cross-attribution agreement export contains method means, not this rank analysis. | Identify actual paired units and rank calculations. |
| `tbl_CH04_metric_validation_expected_vs_observed.tex` and `tbl_CH04_metric_validation_rank_correlation.tex` | Expected ordering requires an independently documented rationale; matching a prespecified ranking alone is not clinical validation. | Trace expected-order source and observed-data generation. |

## Priority 3: image selection and final figure lineage

| Dissertation artifact | Issue | Required resolution |
|---|---|---|
| `fig_CH04_ISIC_0031745_gradcam_sorted_edi_comparison.png` | Representative selection, configuration, map paths and displayed ordering are not yet locked to verified map hashes. | Create selection manifest with exact model/image/map identities and EDI. |
| `fig_appendix_c_gc_gcpp_verified_examples_four_column.png` | P10/P50/P90 examples need exact selection and map/input provenance; filename claiming verified is insufficient. | Trace percentile cohort, selected records, map hashes and model-input image. |
| `fig_CH04_overall_classification_performance_by_preprocessing.png` | Uploaded overall means reproduce from 96 model records; no exact byte match with final dissertation figure. | Link final plot to verified model-level dataframe. |
| `fig_CH04_dataset_specific_roc_auc_by_preprocessing.png` | No exact export/dissertation byte match; final rendering lineage unresolved. | Verify final series against model-level dataset aggregates. |
| `fig_CH04_resolution_specific_roc_auc_trends.png` | Same final-rendering lineage issue. | Verify final series against model-level resolution aggregates. |
| `fig_CH04_classification_performance_metric_heatmap.png` | Same final-rendering lineage issue; verify annotated values and color normalization. | Link final plotting dataframe/code. |
| `fig_CH04_performance_stability_tradeoff_by_preprocessing.png` | Mean inputs are traceable but final figure lacks exact export identity. | Verify coordinates, labels and final rendering. |
| `fig_CH04_performance_stability_quadrants.png` | Not supplied among Chapter 4 exported figures; requires final model-level coordinates and median cutoffs. | Trace generating notebook and plot data. |

None of the 11 PNGs in the uploaded Chapter 4 export ZIP is byte-identical to a PNG in the uploaded dissertation package. This does not demonstrate numerical or visual disagreement: formatting, metadata or rendering changes can alter hashes. Exact final figure lineage remains open.

## Additional validation artifacts

- `figure_edi_synthetic_perturbation_response.png/.pdf` (v5): bundle numerically consistent, 600 sources and 18,600 rows. Shaded bands are observed 2.5th–97.5th percentiles, not mean confidence intervals. Do not claim universally monotonic response; translation is nondecreasing for about 77.3% of sources. Final dissertation placement/source-map lineage remains separate.
- `figure_metric_agreement_heatmap.png/.pdf` (v5): summary reproduces within numerical precision; associations concern metrics on the same synthetic pairs.
- CAM fallback robustness tables/figures: saved statistical analysis exists, but its requested map-array audit did not complete because path fields were absent. Do not describe the whole notebook as fully completed.

## Confirmed findings to preserve

The canonical 23,040-row source CSV SHA-256 is `6f4d3d947e06d3a6f4d9673c9da3a1eaa5fafd944b2bb7d2c440a45b52357bf7`. All EDI values match the separate corrected internal manifest. Chapter 4 preprocessing/resolution/dataset export means and row-bootstrap intervals reproduce; overall classification means reproduce from 96 distinct records. These checks establish numerical aggregation consistency, not complete attribution or training provenance.

## Recommended order

1. Resolve final EDI confidence-interval generation and performance–stability inference.
2. Reconcile final weight-sensitivity tables against complete metrics.
3. Audit complementary metrics and representative-map selections.
4. Link every final dissertation figure to a generating notebook, source hash and selected/aggregated rows.

Preserve original files; write audit outputs separately. No retraining or attribution regeneration is required for the first two steps.
