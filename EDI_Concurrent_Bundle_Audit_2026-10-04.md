# Matched-initialization and six-method bundle audit — October 4, 2026

## Audit decision

The later matched-initialization saved-map study passes full numerical reproduction. The prospective six-method generation passes the compact-bundle checks; full-cohort raw-array numerical replay remains pending because only the prespecified 36-map smoke sample was included. These are distinct studies using distinct model sets. Dissertation revisions remain on hold until this final verification step and joint evidence review are complete.

## Matched-initialization saved maps

- All 728 checksum-listed files verified.
- All 720 saved-map audit copies are present, finite and nonconstant, with 7×7 spatial dimensions. Reconstructed `.npy` byte hashes match the current source-array fingerprints.
- All 2,160 comparisons independently reproduced from those arrays. Maximum errors: Pearson 1.11e-16, SSIM 1.11e-16, EDI 2.22e-16.
- Nine model fingerprints and matching archived completion records were reported by the Colab audit. Models themselves were not included or reloaded in this review.
- The audit preserves the established matched-initialization uncertainty results. It adds numerical reproduction of current saved maps; it does not recompute initial-weight arrays or retrospectively bind historical generating models to attribution arrays. Recorded initialization digests remain recorded evidence.

## Six-method prospective cohort

- All 2,218 checksum-listed files verified.
- Complete plan and metadata: 2,160 maps, 40 images (20 per class), three fixed baseline models, three input conditions and six methods. All task signatures, engine/runner hashes and endpoint identities match.
- All 1,440 exported pairs checked for EDI formula, same-model pairing, prediction linkage, fallback flags, undefined outcomes and common-support membership.
- All 360 current prediction records verified against exported saved predictions. Maximum probability parity error 1.3113e-6, below the predetermined 1e-5 tolerance. Bridge parity error zero. Pre/post source-asset reports retain all 132 matches.
- The compact bundle contains 36 raw-map arrays, all reused from the verified smoke cases. Independent normalization discrepancy is at most 1.11e-15; IG/SHAP RGB tensor aggregation discrepancy zero. All 22 defined sample comparisons reproduced; two undefined sample comparisons retained. Maximum sample EDI discrepancy 2.29e-16.
- Every one of the 2,160 output arrays was fingerprinted by the generation runner, but independent full-array reproduction cannot be inferred from this 36-map sample. The companion CPU notebook reads every saved array on Drive and independently replays normalization and paired metrics.

The source hash remains `b6240f4c7e3c32ba6177ac73d27c37aa1952dbec0f20dcfe208b8200680043fb`. GradCAM++ is the declared first-gradient-power approximation; EigenCAM is class-independent; ScoreCAM uses positive-clipped increases in melanoma probability relative to black input; IG uses 128 trapezoidal steps; SHAP uses the declared Partition/Owen hierarchy and 2,048-evaluation budget. These are implementation-specific comparisons, not universal method rankings. The copied planning specification retains an earlier proposed-stage status label; execution status is documented separately by the locked implementation, runner and completion records.

## Undefined maps and support

All 33 constant maps are ScoreCAM maps on non-melanoma images. They yield 46 undefined comparisons (23 per preprocessing condition). ScoreCAM has 97/120 defined pairs per condition; the other five methods have 120/120.

Common support is defined at the same image/seed/condition and retains 194/240 units overall, or 97/120 per condition. Each condition retains 60 melanoma and 37 non-melanoma model/image observations. These are correlated observations from fixed models, not 97 independent images. Removing undefined ScoreCAM outcomes changes class composition and can change summary means. Available-support and common-support summaries must therefore be reported together.

GradCAM has 35 signed-fallback maps among 360 maps, all nonconstant. ScoreCAM's 33 fallback flags correspond to its invalid constant outcomes; they are not an additional set of valid signed maps. Other methods have zero fallback flags. No IG residual exceeded the runner's declared completeness flag threshold; maximum observed absolute residual is 0.0113206. This does not establish exact integration or validate other explanation properties.

## Descriptive mean EDI

These pooled means describe disagreement for the three fixed evaluated models. They do not establish localization, faithfulness, clinical usefulness or added value. Uncertainty for cross-method contrasts has not yet been calculated in this audit.

| Method | Dullrazor available | Dullrazor common | Telea available | Telea common |
|---|---:|---:|---:|---:|
| GradCAM | 0.1704 | 0.1309 | 0.1702 | 0.1327 |
| GradCAM++ approximation | 0.1306 | 0.1132 | 0.1396 | 0.1198 |
| EigenCAM | 0.1714 | 0.1437 | 0.1749 | 0.1468 |
| ScoreCAM | 0.1275 | 0.1275 | 0.1390 | 0.1390 |
| Integrated Gradients | 0.3231 | 0.2934 | 0.3462 | 0.3209 |
| SHAP Partition | 0.2487 | 0.2189 | 0.2560 | 0.2268 |

Available/common support is 120/97 for each method and condition except ScoreCAM, whose available/common support is 97/97. The method with the smallest available mean changes under common support for Dullrazor, illustrating why missing outcomes cannot be ignored.

## Next step

Run `EDI_Six_Method_Full_Saved_Array_Replay_Audit_v1.ipynb` in a separate CPU Colab session. It reads the completed study, locks source tables to the reviewed bundle hashes, independently reconstructs all normalized maps and checks all 1,440 paired outcomes. It writes a new audit folder and small ZIP; no training, inference, attribution generation or source repairs occur. Upload the ZIP even if a check fails.

After replay review, integrate the six-method cohort, verified ISIC localization results and matched-initialization evidence analytically before proposing dissertation edits. Keep prospective findings separate from frozen historical records. An association between EDI and prediction/localization changes does not establish incremental predictive value.
