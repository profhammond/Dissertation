# Authoritative continuation checkpoint — 2026-10-02

## Goal and constraints
Audit dissertation data, tables, and figures; refine claims only against inspected evidence. User works in Colab with Google Drive. Proceed one task at a time. Do not rerun completed experiments, retrain models, generate new attributions, overwrite canonical tables, or replace manuscript figures during read-only audits. Repository is a prepared private starter, not published.

Current uploaded dissertation is HAMMOND_DISSERTATION (10).zip. Its main.tex specifies March 2027 and Department of Computer Science; use current manuscript contents over older remembered dates or affiliations.

## Established findings
- Internal integration manifest: 23,040 rows; six attribution methods and four internal configurations. 7,680 CAM comparisons numerically reproduced; other 15,360 remain unresolved.
- CAM recovery partitions: 5,760 native pairs plus 1,920 HAM→ISIC pairs, covering all 7,680. Transfer recovery generated 320 baseline maps from saved models, with no retraining. This earlier recovery is completed; do not repeat.
- Uploaded remediated CSV SHA-256 is 36ab13e5027af405700859923c17149b9e18140443e54b76a274d6057a9f5ab7. Its metrics and baseline IDs exactly agree with integrated CAM rows after case normalization of image IDs while preserving suffixes.
- Cohort check passed: exactly 40 image IDs and recorded paths match all 11 supplied attribution CSVs; 192 CAM experiment-method groups each contain all 40. This does not hash image bytes.
- CAM implementation uses adaptive SSIM windows 3/5/7 and signed-map fallback when ReLU empties a map; disclose that algorithm behavior. Recorded constant maps are absent.
- Remaining-method historical audit v2 reproduced no complete canonical metric triples. Candidate existence alone is insufficient. Baseline configuration mismatch affects 11,520 remaining-method rows.
- Progress exports establish that IG and SHAP canonical metrics already appear in per-model files. Eigen-CAM and Score-CAM each have 2,880 progress rows with missing SSIM later filled in consolidated tables; Pearson unchanged. Untitled38 cell 24 is an adaptive-window repair hypothesis; its saved repair outputs reported zero rows repaired, so actual historical execution is not established.
- Dissertation claims 252 models / 51,840 comparisons / nine configurations. Current internal evidence alone cannot substantiate full corpus; external evidence still required. Do not infer the claims are false merely because evidence is absent.
- Primary EDI = (((1-Pearson)/2)+(1-SSIM))/2, theoretical range [0,1.5]. Lower EDI denotes stability, not correctness or clinical benefit.
- Manuscript attribution-method mean table agrees with internal CSV to six decimals, but numerical table agreement does not validate unresolved map provenance.
- Later remediation notebook plotting cells reference legacy EDIResultsDF.csv and heatmap folders. Figure lineage remains unresolved. Appendix includes are commented out in inspected main.tex.

## Active task
Task 2: EDI_Adaptive_SSIM_Repair_Reproduction_v1.ipynb is running in user Colab. Await its compact output bundle and inspect it before selecting the next repair. It tests Eigen-CAM and Score-CAM recorded versus uniquely identified intended pairs, preserves source files, and does not authorize substitutions. Missing/ambiguous maps remain unresolved.

## Next actions after output review
1. Check complete key coverage, source hashes, read errors, metric error tolerances, and numerical matches separately for recorded and intended pairs.
2. Resolve remaining map versions/pair identity for IG/SHAP and unresolved CAM-method pairs using evidence, not matching scores alone.
3. Trace every dissertation table and figure to row selection, source data, generating code, and map hashes.
4. Audit external corpus, classification/training counts, bootstrap design, and pilots independently.
5. Revise manuscript claims and restore appendices only after evidence mapping.

## Files to provide in a new chat
This repository snapshot plus the newest compact output bundle, current dissertation ZIP, and source notebook relevant to the active task. Original maps/weights remain on Drive. Hash inventory lists uploaded inputs available at this checkpoint; it does not include image/map bytes held only on Drive.
