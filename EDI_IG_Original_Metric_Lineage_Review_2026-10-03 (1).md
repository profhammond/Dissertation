# IG original metric lineage review — October 3, 2026

Reviewed source: edi_ig_original_metric_lineage_v1_20261003T232131_222087Z_compact_bundle.zip. Completed status; 3,840 frozen target rows; 197 candidate files, 196 present, one absent, zero read errors. No originals modified; no fresh local raw-map computation.

## Established recorded metric lineage

All 96 per-experiment IG result CSVs contain 40 matching target keys each. All 3,840 Pearson/SSIM/EDI triples equal the frozen dissertation targets, with reported maximum absolute errors of zero and no duplicate source rows withheld. The four aggregate sources also match all 3,840 triples: edi_exports/tables/AttributionResultsDF_IG.csv, Attribution_files/AttributionResultsDF_IG.csv, analysis/dataframes/AttributionResultsDF_IG.csv, and manifest/AttributionManifest_P5P6Analysis.csv. These are duplicate records of the same cohort, not additional independent reproductions.

All 96 saved DONE records report completed_count 40, skipped_count 0, failed_count 0. Their completed_at fields range from June 9 to June 20, 2026. These are stored completion claims, not immutable proof of runtime/model/map identity. The result CSV schema contains experiment_id, baseline_experiment_id, image_id, image_path, preprocess, resolution, attribution_method, pearson_corr, ssim, edi. It contains no attribution-map path or map hash. The inspected DONE payloads identify baseline experiment IDs but not map hashes. Thus original metric exports have been recovered and matched, while historical map identity remains unresolved.

## Baseline provenance

The 96 DONE records identify one baseline per resolution: r128 uses train_ham_test_isic_baseline_r128_20260521_223809; r160 uses ham_baseline_r160_20260515_045725; r192 uses ham_baseline_r192_20260517_115647; r224 uses ham_baseline_r224_20260519_165246. Each baseline serves 24 experiments. 72 of the 96 status records have a baseline configuration different from their comparison experiment (equivalent to 2,880 reported completed image comparisons); 24 are configuration aligned. These records corroborate the recovered producer's resolution-only baseline selection. Configuration alignment still does not establish model identity.

## Filename correction

The earlier generic IG test reported 24 missing candidate rows for isic_0015232_downsampled. This audit found the actual file at edi_exports/heatmaps/ham_baseline_r160_20260515_045725/ISIC_0015232_downsampled_heatmap.npy. The earlier notebook uppercased the suffix, so those 24 missing-path outcomes were caused by the constructed filename. They are not evidence of missing original data. The located file's SHA256 is 48510f94de891eb3b0dee0aa6e0c7a10fa3107b99c84a51191c4286f6cf55cfe, identical to 28 of the 39 previously read generic baseline files. This does not establish its method identity or make the generic baseline a valid IG baseline. The 936 previously computed rows still had zero complete frozen-target matches under either protocol; the remaining 24 have not been calculated by that audit.

## Implications and next investigation

The frozen IG values agree with the saved per-model producer records, so the reviewed evidence does not indicate an aggregation transcription error. Current recorded-map recomputation still does not reproduce those frozen values. Direct evidence of later path patching remains relevant but does not fully explain the discrepancy. Preserve all original metrics and maps; no canonical replacement is authorized.

Next recover the full IG producer notebook's saved execution outputs and exact map-write/load/cache logic. Check whether baseline or comparison files were overwritten, whether comparison metrics used in-memory arrays that differed from saved maps, and whether source notebook versions differ from executed code. Do not select arbitrary maps by numerical agreement. A separate path-only correction can cover the 24 generic candidates if needed, but cannot resolve method/model provenance by itself.

Add this review and the original compact bundle to the dissertation repository as an entry after the October 3 18:49 ET checkpoint. That checkpoint remains useful for continuity but predates these findings.
