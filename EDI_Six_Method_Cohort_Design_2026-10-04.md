# Six-method prospective cohort design — 2026-10-04

## Evidence-based model choice

Use the earlier HAM r224 factorial/repeatability asset set as the initial candidate, not the later matched-initialization set. Its current 9 models, 40 original images, 80 preprocessing caches and 2,400 existing CAM comparisons have successful current-asset checks; 960 saved predictions reproduce within 1e-5, maximum error about 1.0133e-6. The later matched-initialization pilot has recorded initial-weight digests but lacks equivalent saved-array/model reproduction in the supplied bundle. These are distinct model sets.

Candidate roots:
- Dissertation/edi_training_repeatability/edi_training_repeatability_ham_r224_v1
- Dissertation/edi_model_input_factorial_counterfactual/edi_model_input_factorial_counterfactual_ham_r224_v1

Choose this set for verified current assets and prior controlled comparison coverage, not for favorable observed EDI values. Existing training transformation lineage is not fully established; fixed-model input comparisons are the primary estimand. Pipeline comparisons, if included, must retain that limitation and must not be described as isolated training effects.

## Locked design

- HAM, 224 x 224, existing 40-image cohort (20 melanoma, 20 non-melanoma).
- Baseline, DullRazor-style and Telea inputs; selected to extend the existing factorial design and its two documented hair-removal approaches, not selected from restricted rankings.
- Fixed melanoma target index 1 for class-conditioned methods. Eigen-CAM is class independent; report that exception explicitly rather than claim it uses a melanoma target.
- Six methods: Grad-CAM, Grad-CAM++, Eigen-CAM, Score-CAM, Integrated Gradients and SHAP. Lock exact implementations before generation. SHAP must name the actual algorithm, masker/background and sampling budget; a generic SHAP label is insufficient.
- Primary: the baseline classifier on original versus each transformed input, separate by seed and method. Three baseline models x three input conditions x 40 images x six methods = 2,160 maps; 1,440 paired comparisons.
- Optional separate extension: all seven model-input cells per seed from the existing two-condition factorial. This is 5,040 maps and 7,200 comparisons across five comparison types. It is not required for the initial fixed-model cohort and must not silently expand runtime.

## Mandatory implementation lock before new attribution generation

Recover the producer's image decode/resize/scaling, exact preprocessing functions, target-layer selection, class-score definition, normalization, signed-map policy, interpolation and SSIM settings. Verify transformations by recomputing caches in a separate prospective output directory and comparing decoded pixel arrays; preserved cache hashes alone do not establish how the transformation was performed.

Record attribution-method specifics: CAM layer and gradient/score formulas; Score-CAM channel selection and masking; IG baseline(s), integration steps, convergence residual and signed channel aggregation; SHAP explainer type, fixed background/masker, random seed and sample budget. Preserve raw attribution arrays as well as explicitly defined 2D maps. Preserve signed outputs and report constant/undefined metrics; do not silently turn them into valid explanations.

No new training is planned. Stop if assets, target mapping or input parity fail. Do not relax thresholds after seeing failures. Current saved-model agreement does not prove historical generating-model identity.

## Outcomes and claim limits

Reuse matched predictions only after current asset hashes and input parity pass. Report EDI and components, probability changes and class switches; include method-specific invalid/fallback rates and independent controls. Cluster uncertainty by image, conditional on fitted models. Forty balanced images support a pilot, not clinical validation, natural-prevalence estimates or population-seed inference.

This cohort addresses six-method comparison and current reproducibility. It does not repair historical maps, and it cannot by itself answer lesion localization without independently verified masks for the same cohort. A stronger-classifier localization replication is a separate task.

## Next deliverable

A Colab preflight/implementation-lock notebook that verifies the chosen assets, recovers preprocessing/attribution specifications and exports a frozen plan. It should generate no attributions, train no models and overwrite no existing files. Only after its compact output is reviewed should the generation notebook be finalized.
