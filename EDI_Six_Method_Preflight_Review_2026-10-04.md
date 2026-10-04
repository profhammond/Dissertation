# Six-method preflight review — 2026-10-04

PASS for current assets, transformation reconstruction and prospective plan integrity.

Input bundle SHA-256: 30ef2c2c6c9949034e03f79bd2854f3df7b8da2e3aab97dabcb9967b17c1eb45.

- All 10 files listed in the bundle checksum ledger verify in size and SHA-256.
- All 132 current asset fingerprints agree with their prior recorded identities.
- All 80 transformed images reproduce exactly at decoded pixel level using the recovered producer function; 40 baseline decode comparisons also agree. Maximum pixel error is zero.
- The cohort contains 40 unique images, balanced 20 melanoma/20 non-melanoma.
- The map plan contains 2,160 unique tasks, complete 40-image coverage in all 54 seed/method/input cells.
- All 1,440 pairs reference valid map tasks with the same model, seed, method, image and label; original versus the assigned transformed input. Model and input fingerprints join exactly to the checked assets.
- Class-conditioned methods target class 1; Eigen-CAM has no class target.

This confirms the current cache transformation lineage and planned comparison design. It does not establish historical training-input lineage, reproduce attribution generation, or validate the proposed attribution implementations. No models were loaded or inference rerun by this preflight. Prior factorial prediction parity is separate evidence, supported by the unchanged current asset hashes.

implementation_generation_ready=False is expected: the methods remain proposed and require implementation-specific validation. Next build a bounded smoke-test notebook for model inputs, target-layer resolution and all six method implementations before full generation. Preserve constant maps and undefined comparisons as outcomes; do not silently drop them or replace them with zeros. Use a deterministic image subset selected by locked cohort order, not results.
