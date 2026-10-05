# External folder inventory review — 2026-10-05

All 633 bundle checksums passed. Six requested roots exist. Histo has four subdirectories but no files recorded. Five domains contain experiment records; their scientific identity and mapping remain subject to configuration verification.

The scan is partial: four dataset directory I/O errors and 52 evidence-copy limit issues were reported. It recorded 66,168 files and 197 table schemas. Missing copied evidence is not evidence of absent source files.

Each populated domain has 28 test-prediction table schemas. Copies available: Fundus 28, CXR 28, ChestXray14 28, SIPaKMeD 10, BreakHis 0. The nested six-method EDI tables have 5,760 rows and 40 image IDs each where copied. BreakHis's separately supplied table has the same dimensions.

## Exact image-ID split matches for nested six-method cohorts

| Domain | Train | Validation | Test |
|---|---:|---:|---:|
| Fundus / APTOS |32|4|4|
| CXR |36|1|3|
| ChestXray14 |33|3|4|
| SIPaKMeD |22|10|8|

These are exact string-ID matches against archived splits, not image-byte verification. Copied test predictions reproduce the test-overlap counts across available runs. BreakHis membership is pending recovery. Alternative 960-row CXR and ChestXray14 EDI tables match six test images each and must remain distinct from nested six-method tables. Fundus also preserves a pre-SSIM-fix table; do not combine versions.

Most EDI images belong to training splits. Their drift–prediction relationships can be descriptive, with explicit in-sample status, but cannot establish held-out classification generalization. Four to eight test images per current nested cohort are insufficient for strong method-by-condition conclusions. Attribution methods and repeated resolutions do not increase the independent image count.

Next: run the CPU record-recovery notebook, verify class mappings, exact image/path identities and comparison configurations, then decide whether to recover cohort predictions with original models or generate a separate locked held-out attribution cohort. Historical model/map identity is not established by this inventory. No training or inference rerun is justified yet.
