# Trauma-Informed Response (TIR) classification in Indonesian text: hybrid BERT-SVR

Annotations (without source texts), data splits, model predictions, and analysis notebooks accompanying the manuscript
**"Beyond F1: Prevalence-Aware Evaluation of Hybrid BERT-SVR for Trauma-Informed Response Classification in Indonesian Text"**
(submitted to JOIV: International Journal on Informatics Visualization).

> **Research use only. Not a diagnostic or clinical tool, and not a suicide-risk detector.**
> The four categories (Intrusive, Avoidance, Arousal/Activation, Negative Cognition & Mood) are non-diagnostic labels for response patterns in text.

## Contents

| Path | Content |
|---|---|
| `data/annotations/` | Psychologist scores (0-1) per text for the four categories, **without the text**: batches 3-5 (files 01, 02, 07, 08, 10, 11), the 200-text re-annotation (03), the 200-text retest (05), the second-session scores for the 271 test texts (06), and the 141-text test adjudication with session 1, session 2, and final scores (09). |
| `data/labels/` | Scores by `ID_teks` for the 1,981 gold texts, the 2,000 natural (pseudo-labelled) texts, the 577 batch-3 texts, the 271 adjudicated ("valid") test labels, and the 130 consensus test labels. |
| `data/splits/` | Frozen train / validation / test assignment of the 1,981 gold texts, the order of the 271 test texts, and the 130 consensus IDs. |
| `data/predictions/` | Test-set (271 x 4) predictions of the BERT-only (seed 42) and hybrid models. |
| `notebooks/` | Analysis notebooks 20-26 (Colab, CPU only) and figure notebooks 27-28: classical baselines, AUC and dominant-label tests, prevalence-aware evaluation, emoji / R2 / near-duplicate checks, ICC of the retest, ICC and consensus verification on the 271 test texts, and the export of the data package. |

## Not included

* **The original texts.** They were collected from Quora and are not redistributed. Rows are keyed by `ID_teks` only.
  The texts are withheld because of the terms of the source platform and the sensitive nature of the content. Researchers who need access for non-commercial research may contact the corresponding author (see the paper). Requests are considered case by case, subject to the source platform's terms and to responsible, ethical use.
* Fine-tuned model weights (large files; available on request).
* Free-text annotator notes.

## Columns

* `ID_teks`: text identifier.
* `Intrusive`, `Avoidance`, `Arousal`, `NegCogMood`: continuous score (0-1) assigned by one clinical psychologist. Binary labels in the paper use score >= 0.5.
* `Anotasi1_*`, `Anotasi2_*`, `Final_*` (file 09): first session, second session, and adjudicated final score.
* `orig_*`, `retest_*` (file 05): original and re-annotated scores for 200 gold texts.
* `skor_kata_kunci*`: keyword-based reference score shown to the annotator alongside each text.
* `text_word_count`, `flag_short_text`: simple text-length descriptors.

See `DATA_CARD.md` for the annotation procedure, set definitions, and limitations.

## Reproducing the analyses

The notebooks were written for Google Colab with a Google Drive layout (`JURNAL-DATASET`, `JURNAL-OUTPUTS`) and need the original texts, which are not included. Score-only analyses (ICC, kappa, session differences, test-set metrics from the provided predictions) can be recomputed from the files in `data/`.

## License

Code: MIT (see LICENSE). Annotations and splits: CC BY 4.0.

## Citation

`[Citation will be added after publication.]`
