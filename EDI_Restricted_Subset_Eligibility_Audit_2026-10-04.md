# Restricted-subset eligibility audit — 2026-10-04

Source: EDI_Frozen_Manifest_Target_Reconciliation_v1 (1).zip.

Frozen target SHA-256: a1c5e55f7ab4935076dad87c77ad45f0f767978cb1583631a279326d12b5cd7c.

## Findings

The inspected ledger contains 30,720 protocol attempts for 15,360 unique internal comparisons across Eigen-CAM, Score-CAM, IG and SHAP. Deduplicate row_id before counting comparisons; protocols are alternative calculations on the same rows.

- 11,520 unique rows have a recorded baseline-ID mismatch; 3,840 do not.
- 3,840 unique rows agree numerically with frozen metric triples under the adaptive protocol: 1,920 each for Eigen-CAM and Score-CAM.
- Of those matches, 960 unique rows have no baseline-ID mismatch: each method contributes 240 HAM r192 and 240 HAM-to-ISIC r128 rows.
- Every protocol attempt records map_model_identity_verified=False and canonical_integration_authorized=False.
- Therefore zero rows in this four-method ledger meet a strict rule requiring both frozen metric agreement and verified map/model identity. The 960 exported candidate rows are leads, not verified eligible records.
- IG and SHAP have no frozen metric matches in this ledger under either tested protocol.

## Separate CAM evidence

The completed recovery/integration chain accounts for 7,680 internal Grad-CAM/Grad-CAM++ comparisons, including 5,760 native and 1,920 recovered transfer comparisons. This is separate evidence, not contained in the four-method reconciliation ledger. A row-level CAM ledger and frozen target join are required before constructing its restricted ranking analysis here. Do not repeat recovery or generate new maps merely to obtain an export.

## Consequence for rankings

A six-method provenance-verified ranking cannot be established from this ledger. Do not present the 960 candidates as a corrected corpus or combine them with CAMs while treating all rows as equally verified. Their method/configuration/resolution support is restricted.

Next obtain the existing CAM integration ledger and exact frozen internal rows, preserving source hashes, reference identities and map provenance. Define eligibility before calculating rankings. Compare restricted versus frozen values on identical configuration/resolution/image support; separately describe differences caused by coverage restrictions. Any remaining transformation-lineage limits must remain visible.

No experiments were rerun, canonical data changed, or new scientific rankings calculated.
