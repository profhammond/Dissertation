# CAM ranking heterogeneity — 2026-10-04

Based on the 7,680 joined internal CAM records. Rankings average 160 comparisons per condition within each configuration/method: four resolutions times 40 images. These are descriptive ranks, not independent-image sample sizes or statistically significant differences.

Only Combined Grad-CAM has exactly the pooled six-condition ordering. Spearman agreement with the pooled ordering ranges from 0.086 to 1.000.

The condition with the lowest mean EDI varies: DullRazor in three groups, Telea in two, Diffusion in two, and Navier–Stokes in one. Therefore the pooled ordering does not establish a universal preprocessing hierarchy, even within this restricted two-method internal subset.

The HAM Grad-CAM diffusion result includes r224, whose training-input transformation lineage remains unresolved. Retain that limitation rather than interpret its low mean as evidence that diffusion causally stabilizes explanations.

No tests of rank differences or multiplicity-adjusted significance were performed. Small mean differences should not be interpreted as reliable separation. This analysis verifies heterogeneity of saved records, not superiority of an explanation method or preprocessing procedure. Lower EDI indicates lower map disagreement.

Next research choice: use one locked configuration/resolution with baseline plus two conditions, selected before new outcomes, to compare all six methods on identical support. Existing factorial and matched-initialization model sets are distinct and must not be substituted. Verify model and transformation lineage before choosing which set supports the prospective cohort.
