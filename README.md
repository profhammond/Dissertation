# Dissertation provenance and reproducibility

Scott G. Hammond — Developing and Evaluating a Reliable Deep Learning Framework for Melanoma Classification.

This repository records audit code, evidence references, and continuity decisions. Begin with [HANDOFF.md](HANDOFF.md), then [TASKS.md](TASKS.md). Status as of 2026-10-02. Audit completion is not equivalent to scientific validation.

## Setup
Create a dedicated **private** GitHub repository named `dissertation-provenance` without an initial README. Extract this package and upload its contents, or use:

```bash
cd dissertation-provenance
git init -b main
git add .
git commit -m "Record dissertation provenance audit checkpoint"
git remote add origin https://github.com/YOUR_ACCOUNT/dissertation-provenance.git
git push -u origin main
```

No repository has been published by preparing this package. Review uploaded file paths before making a repository public. No license is selected; choose one before public code distribution.

## Colab workflow
Open the required notebook in Colab. Audit notebooks use `/content/drive/MyDrive/Dissertation` and depend on completed prior audit outputs. Run only the next task listed in the handoff; preserve originals. Store large maps, weights, and images in Drive. After inspecting each returned bundle, update status, evidence references, and handoff together in one commit.

## Continuity
For a new chat provide HANDOFF.md, TASKS.md, the current commit identifier, and the relevant compact output bundle. A repository URL alone may not grant access to a private repository. The ZIP snapshot can also be uploaded directly.

## Contents
- `notebooks/`: four continuation audit notebooks; the newest remains pending output review.
- `docs/`: earlier detailed audit reports, retained as dated historical checkpoints.
- `evidence/`: SHA-256 inventory and bundle status snapshots.
- `registers/`: initial table and figure provenance tracking.

Hashes identify supplied files; they do not prove model identity, original execution, or scientific validity. Historical Drive paths are references, not files included here.
