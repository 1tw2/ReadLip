# ReadLip: Identity robust talking face generation with semantically consistent articulation

**Status: research implementation scaffold, NOT a verified end-to-end ReadLip reproduction.**

This project builds on the official [TalkLip](https://github.com/Sxjdwang/TalkLip)
repository (CVPR 2023). Keep the TalkLip README and attribution when distributing.

## Implemented components

- `readlip/disentanglement.py`: content/speaker encoders and projections, GRL,
  Stage I supervised/fusion/adversarial/orthogonality terms; four-way Stage II
  recombination with frozen classification heads.
- `readlip/losses.py`: dual-branch contrastive synchronization, reference mouth
  copy suppression, ArcFace-embedding identity suppression, weighted generation loss.
- `readlip/training.py`: dependency-injected example for two generator branches,
  matched reconstruction and cross-identity losses.
- `tests/`: unit tests for mathematical helpers.

## NOT yet implemented/integrated

Upstream TalkLip's `train.py`, `inf_test.py`, `inf_demo.py` are **unchanged**.
A full training pipeline additionally requires true LRS2 pseudo speaker labels,
Golden Gemini speaker backbone, Whisper decoder adapters, speaker-distinct
pair sampling, generator input/channel matching, AV-HuBERT and face-recognition
preprocessing, weights, optimizer schedule, and real full-scale training tests.

The paper does not specify numerical `temperature`, `identity_margin`,
`copy_margin`, or `copy_threshold`; supply values from actual training records.
Do not present this bundle as reproducing reported metrics without verification.

## Quick check

```bash
python -m pip install torch pytest
python -m pytest -q tests
```

## Attribution

Original TalkLip: https://github.com/Sxjdwang/TalkLip
