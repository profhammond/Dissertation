# Annotated ISIC source-lineage review — October 4, 2026

Mask extraction provenance is now supported for all 100 locked annotations. Image downsampling lineage and localization eligibility remain unresolved.

## Verified evidence

Source bundle: `edi_annotated_isic_source_lineage_v1_20261004T172626_512505Z_compact_bundle.zip`.

All 14 file checksums and sizes passed. The 100 locked image/mask fingerprints exactly match the prior v1.1 prediction audit. Each mask has exactly one matching archive member, and all 100 member SHA-256 values equal the corresponding locked mask hashes.

The saved ground-truth archive SHA-256 is `99f8b2bb3c4d6af483362010715f7e7d5d122d9f6c02cac0e0d15bef77c7604c`, identical to the September 10 acquisition record. That record identifies the ISIC challenge S3 URL and official challenge page. Together, the acquisition record and member hashes support consistent extraction from the recorded archive. The archive itself was not independently downloaded/authenticated in this audit; member pixel bytes are not included in the compact bundle for independent local recomputation.

## Search limits and interpretation

The search visited 2,520 directories, read 482 source files and approximately 100 MiB, and exported 22 matching blocks. The displayed `bounded_search_completed: true` means the directory queue emptied; it does not mean all eligible source files were read. The exclusion ledger records 4,102 files skipped under `byte_limit`, which combines the per-file and aggregate byte limits, 285 excluded directories, 210 maximum-depth exclusions, and one directory input/output error. The latter is not included in `source_read_errors: 0`, which counts only file-read errors.

Most exported leads concern recent audit notebooks, historical alias handling, or downstream use of the selected cohort. None of the recovered blocks establishes the producer of the current downsampled images. Matching source terms must not be treated as an executed code-to-asset link. In particular, the current audit itself and the alignment audit appear among the leads.

A relevant excluded source is `EDI_Paired_Localization_Cohort_Builder_Readiness_Audit_V2.ipynb` under MyDrive/Colab Notebooks. Other skipped leads include `Notebook 02 — Artifact and Lesion Mask Preparation.ipynb` and `NB11_Cross_Domain_EDI_Generalization_Analysis.ipynb`. Their contents have not been inspected in this returned bundle.

## Decision

The official-mask acquisition/extraction chain is substantially better documented. It does not by itself establish registration between those masks and the selected ISIC2019 image copies, especially the 74 dimension-mismatched pairs.

Keep the completed classification audit unchanged and localization eligibility pending. The next task is a targeted, source-cell-focused inspection of the skipped cohort-builder and dataset-preparation notebooks, prioritizing image download paths, filename changes, crop/rotation behavior, resize dimensions/interpolation, JPEG encoding, and saved producer logs. This avoids another general scan and does not require training or attribution generation. If the producer cannot be recovered, report a future direct-resize localization analysis as provisional with its assumptions and sensitivity checks rather than claiming historically verified alignment.
