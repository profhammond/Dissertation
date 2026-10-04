# CAM restricted analysis — 2026-10-04

Recovered the original integration bundle; SHA-256 matches recorded identity 4f967ce3365eb863fc931ff7b7d521c3a1c3ce4dbfbb546e4fdb2645833f86e7.

All 7,680 Grad-CAM/Grad-CAM++ rows join uniquely to the 51,840-row formulation-audit export using experiment ID, case-normalized image ID (suffix preserved), numeric resolution, and normalized method. No duplicate keys or missing joins. Pearson, SSIM, primary EDI and baseline experiment IDs agree exactly for every joined row. The integration ledger records map_provenance_verified=True for all 7,680.

The frozen-data derivative used here is dissertation_manifest_recalculated_alternative_formulations_v1.csv from CH05_Formulation_Provenance_Audit_v1.zip; SHA-256 0545b3a3b78a25ca140356f263d52ba9fd4d910b00cfd60cb65339bd3fd0043a. Its identity is distinct from the original frozen manifest SHA-256 a1c5e55f7ab4935076dad87c77ad45f0f767978cb1583631a279326d12b5cd7c. Do not describe the derivative as byte-identical to the original manifest.

Coverage: four internal configurations, four resolutions, six transformations, two methods, 40 images per cell. Each configuration/method has 960 rows. The accompanying rank table averages each preprocessing condition over the four resolutions within configuration and method (160 rows per condition), with lower mean EDI ranked first.

These ranks reproduce the same frozen CAM records on common support: provenance integration changes no metric or baseline ID in this join. Removing four unresolved methods or external configurations changes analytical coverage; ranking differences from that removal cannot be attributed solely to provenance corrections.

Limitations: this verifies joins and saved numerical records, not fresh array computation or historical training reproduction. The predecessor recovery supports the CAM map-path chain; all historical training/input lineage is not thereby established. In particular HAM diffusion r224 retains a transformation-lineage question. Six-method ranking robustness remains unresolved. Lower EDI means less disagreement, not better explanations or classification.

Next: inspect configuration/method-specific ranks, then decide whether a prospectively locked six-method cohort is needed. No models retrained, maps generated, or canonical files overwritten.
