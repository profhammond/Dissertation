# Historical generic IG baseline audit review — October 3, 2026

Source: edi_historical_generic_ig_baseline_v1_20261003T224925_290828Z_compact_bundle.zip. Completed status, 960 unique target keys, 1,920 protocol attempts; frozen reference SHA a1c5e55f7ab4935076dad87c77ad45f0f767978cb1583631a279326d12b5cd7c. Reviewed saved results and map fingerprints; no fresh local map computation.

## Results

Each protocol calculated 936 rows and reported 24 missing generic baseline candidates. Neither protocol reproduced any complete frozen metric triple at tolerance 1e-4. These are the same 960 target rows under two protocols, not independent cohorts. Adaptive errors were finite across 936 rows, with mean absolute EDI error 0.330317. Legacy SSIM was undefined for all 936 calculated rows, consistent with the default window exceeding the 5×5 baseline extent. Legacy Pearson and EDI were finite for only 264 rows. Undefined legacy values must remain distinct from finite numerical discrepancies.

39 unique generic baseline files were read, all float32 5×5 with no nonfinite entries. 936 unique comparison files were read, all float32 160×160 with no nonfinite entries. Dimensions alone do not establish the attribution method, but these generic baselines must not be treated as verified IG maps. No model identity was established, and no canonical integration is authorized.

702 calculated rows use a HAM baseline for another evaluation configuration; 234 calculated rows are HAM. Both groups had zero matches. Including missing candidates, the cohort contains 720 mismatched and 240 configuration-aligned rows. Configuration alignment does not establish model identity.

The 24 missing candidate rows all concern image ID isic_0015232_downsampled, referencing one constructed generic filename. The notebook uppercases the full identifier, yielding ISIC_0015232_DOWNSAMPLED_heatmap.npy. The historical example only established the case convention for an ordinary ISIC identifier; existence of a differently cased suffix or another historical path has not been checked. Thus report absence at the tested path, not proven absence of the original map.

## Interpretation and next action

The earlier generic baseline template does not recover the frozen IG results for the 936 available pairs. This does not negate direct notebook evidence of paths being patched without metric recomputation; it leaves the original metric/map lineage unresolved. Preserve the frozen results and all source maps. Do not loosen tolerance, promote these generic maps, or replace dissertation values from this test.

Next investigate the original IG producer's metric-writing outputs and progress-result references, together with baseline selection and any later map overwrites. Recover an explicit earlier metric export/map association rather than searching arbitrary candidates for a numerical match. Separately verify the missing downsampled filename's actual casing. The repo checkpoint dated 18:49 ET predates this result; add this review and the original compact bundle as a subsequent audit entry.
