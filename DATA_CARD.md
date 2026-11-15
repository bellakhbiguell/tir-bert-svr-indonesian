# Data card

## Purpose
Annotations for studying non-diagnostic Trauma-Informed Response (TIR) categories in Indonesian reflective text. The categories are labels for response patterns in text, aligned with PTSD symptom clusters as described in the manuscript, and are not diagnoses.

## Source texts
Public Quora posts collected by keyword scraping. Texts are not distributed in this repository. No user identity is included.

## Annotation
* One clinical psychologist assigned a 0-1 score for each of the four categories. A keyword-based reference score was shown alongside each text in both annotation sessions.
* The category definitions and indicators (Table II of the manuscript) were drawn up by the first author from the DSM-5 symptom clusters and cognitive models of PTSD, then used as a written guideline, which the psychologist reviewed and approved before annotation.
* Single annotator: no inter-annotator agreement exists.

## Sets
| Set | n | Notes |
|---|---|---|
| Gold | 1,981 | Primary annotations (1,575 train, 135 validation, 271 test indices); 1,573 train texts remain after leakage removal. |
| Test | 271 | Session 1 = frozen gold scores (`data/labels/gold_1981_data_ahli.csv`, split `test`). Session 2 = `data/annotations/06_anotasi_test_271.csv`. |
| Consensus | 130 | Test texts whose dominant (highest-scoring) category is the same in both sessions. |
| Adjudicated ("valid") | 271 | Consensus texts (130, score = mean of the two sessions) plus the 141 texts whose dominant category differed between sessions, adjudicated by the psychologist (final scores in file 09). |
| Validation | 135 | Used for all tuning. |
| Retest | 200 | Gold texts re-annotated in a separate session (files 03 and 05). |
| Batches 3-5 | 577 / 564 / 600 | Additional training annotations after duplicate removal (batch 3 in `data/labels/`; batch 4-5 per-category score files in `data/annotations/`). |
| Natural | 2,000 (1,999 used) | Pseudo-labels from an early-stage model, used only as extra training data. |

## Known limitations
* One annotator. Intra-rater agreement is low (Cohen's kappa 0.03-0.40; ICC for absolute agreement 0.09-0.45). The second session scored lower on average in every category, most strongly for Avoidance.
* The keyword score was shown in both sessions, which may inflate agreement.
* The test and validation sets were inherited from an earlier project version (fixed indices).
* Scores are not calibrated; binarization at 0.5 is unstable, especially for Avoidance.
* The category adaptation has not been validated against an established clinical instrument.

## Intended and out-of-scope use
Intended: research on non-diagnostic text classification and evaluation methodology. Out of scope: diagnosis, clinical decision-making, or detection of suicide risk in individuals.
