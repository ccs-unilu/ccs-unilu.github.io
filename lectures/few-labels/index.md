# CCS 2026 - Learning with Fewer Labeled Examples

Materials for the lecture on May 22, 2026.

The day works through the PML book's Chapter 19 in code, on motor imagery EEG (PML 19.1 through 19.7).

## Day plan

| Slot | Time | Notebook | PML |
|---|---|---|---|
| 1 | 10:00–12:00 | `01_single.qmd` - Working with What You Have | 19.1, 19.3, 19.7 |
| – | 12:00–13:00 | Break | - |
| 2 | 13:00–15:00 | `02_transfer.qmd` - Help from Other Datasets and Tasks | 19.2, 19.6 |
| – | 15:00–15:15 | Break | - |
| 3 | 15:15–17:00 | `03_active.qmd` - Asking Smarter Questions | 19.4, 19.5 |

All the notebooks are self-contained. But you can reuse the pretrained model from `02_transfer` in `03_active`.

## Topics

- **Squeeze your own data**
  - Better features (Riemannian tangent space for EEG)
  - Data augmentation - PML 19.1
  - Semi-supervised pseudo-labeling - PML 19.3
  - Weakly supervised label smoothing - PML 19.7
- **Help from other datasets/tasks**
  - Cross-subject transfer + fine-tuning - PML 19.2
  - Frozen pretrained features (EEGNet penultimate) - PML 19.2 (frozen, deep)
  - Few-shot calibration - PML 19.6
  - Pretrained features outside EEG (optional text coda) - PML 19.2 (cross-domain)
- **Smarter strategies**
  - Active learning (uncertainty sampling) — PML 19.4
  - Meta-learning (MAML) — PML 19.5


## Resources

- Dataset: PhysioNet Motor Imagery, two classes (left vs right hand)
- Data loader: MOABB
- Model: EEGNet from braindecode package
- For the optional text analysis: sentence-transformers on DSM-5 symptom descriptions (4 categories, 10 each)
- For the MAML: learn2learn
- Compute: free Colab

To render the slides and convert the notebooks, run:

```bash
quarto render slides.qmd --to revealjs
quarto convert 01_single.qmd  # OR jupytext --to ipynb 01_single.qmd
```
