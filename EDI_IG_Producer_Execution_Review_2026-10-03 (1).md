# IG producer execution and map persistence review — October 3, 2026

Source bundle: edi_ig_producer_execution_evidence_v1_20261003T235217_805100Z_compact_bundle.zip. Source notebook /content/drive/MyDrive/Colab Notebooks/IG_only.ipynb, SHA256 c15f4f7b034159131fcee33c88b0b7560f6bb6d2356075248bff3aa7a554a32c. Audit completed; exact reviewed hash; 32 cells, 21 with retained textual output. The producer was not executed by this audit.

## Source evidence

The extraction loop in zero-based cell 18 computes baseline and experiment maps in memory, compares them, saves only the experiment map with np.save, then appends the metric row to aggregate and per-model CSVs. Across the full 32-cell source there is one np.save occurrence and zero np.load occurrences. No baseline-map persistence call appears. This establishes the behavior of the recovered source version, not immutable historical runtime behavior.

The recovered IG implementation uses a zero input reference and 50 interpolation samples; averages gradients, takes mean absolute channel attribution, resizes to input dimensions, and normalizes. Model selection and resolution-only baseline selection remain provenance concerns. No model hashes or original baseline-map hashes are supplied by this notebook.

## Retained execution evidence

Cell 18 output selects seven IG resume candidates, then reports Incomplete models to run: 0 and ValidModelsDF after incomplete-only filter: 0. Therefore the retained output for this invocation records no new attribution comparisons. It is not evidence of a fresh 3,840-row generation run.

Earlier retained outputs record 90 result files, 89 DONE files, and one 35-row partial result; subsequent output records deletion of that partial result and rebuilding an 89-experiment, 3,560-row aggregate. Later analysis output (cell 21) loads the completed 3,840-row, ten-column IG aggregate. These outputs document saved states of a repair/resume and analysis workflow. Their execution_count fields are absent for most relevant cells, and they do not reconstruct the chronology or code identity of every original generation event. The recovery cell also includes code capable of rebuilding DONE records from saved CSVs; consequently a DONE record alone must not be treated as immutable proof of execution.

## Combined evidence and status

The prior original metric lineage audit established exact equality of all 3,840 frozen IG triples with 96 per-model result CSVs. The current evidence confirms that the recovered producer source does not preserve the baseline arrays used for the comparison. Later Missing_heatmap notebook code generated method-specific baseline maps and patched paths without recomputing stored metrics. Those later maps cannot be assumed identical to the original in-memory arrays. Neither reviewed protocol reproduced frozen IG targets from the current recorded maps; testing the documented generic r160 baseline template also did not recover any complete target triple for the 936 calculated rows. The additional 24 generic rows were omitted by a filename capitalization error, not missing original data.

This is a documented historical baseline-map provenance gap. It is not proof that every current map was overwritten, that the original metrics were incorrect, or that path patching alone caused every discrepancy. IG status: recorded metric/export lineage verified; original baseline array identity unresolved; current raw-map numerical reproduction of frozen targets not established; baseline configuration mismatch documented; canonical replacement/integration not authorized.

## Next action

Record this status explicitly in the repository and dissertation provenance qualifications. Avoid further arbitrary candidate searches or changing metrics to match current repaired maps. If a contemporaneous notebook version, baseline array archive, or original map hashes are recovered, review them as new evidence. Otherwise the historical identity gap remains a limitation. Continue the remaining-method audit with equivalent original metric/progress lineage checks for SHAP, followed by Eigen-CAM and Score-CAM as needed. Historical gaps should be separated from the already completed table/formula/figure calculations and the 7,680 reproduced Grad-CAM/Grad-CAM++ comparisons.

This review and its original compact source bundle postdate the October 3 18:49 ET repository checkpoint. Preserve both as an additional dated entry.
