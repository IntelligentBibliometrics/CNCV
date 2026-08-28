# CNCV Data

This directory contains the data files for the Claim-Normalized Citation Verification (CNCV) dataset. All files are UTF-8 encoded in JSON Lines (`.jsonl`) format, with one JSON object per line.

## Files

| File | Records | Description |
|---|---:|---|
| `TRAIN.jsonl` | 1,154 | Training split |
| `DEV.jsonl` | 146 | Development/validation split |
| `TEST.jsonl` | 144 | Test split |
| `corpus.jsonl` | 1,444 | Sentence-segmented cited documents linked to the dataset samples |

## Split fields

Each record in `TRAIN.jsonl`, `DEV.jsonl`, and `TEST.jsonl` contains:

- `claim`: original citing claim
- `citation_marker`: citation marker associated with the claim
- `normalized_claim`: human-normalized claim
- `gold_evidence_ids`: zero-based indices of gold evidence sentences in the corresponding corpus record
- `gold_evidence`: gold evidence sentences
- `source_file`: identifier linking the sample to `corpus.jsonl`
- `label`: six-class citation label
- `label_3`: three-class label
- `type`: dataset split (`TRAIN`, `DEV`, or `TEST`)

Each record in `corpus.jsonl` contains a `source_file` identifier and an ordered `sentence` array. A split record is linked to its corpus record by matching `source_file`.

## Labels

| `label` | `label_3` | Meaning |
|---|---:|---|
| `ACCURATE` | 0 | Accurate |
| `PARTIALLY_SUPPORTED` | 1 | Minor error |
| `UNRELATED` | 2 | Major error |
| `PERIPHERAL` | 2 | Major error |
| `MISREPORTED` | 2 | Major error |
| `CONTRADICTED` | 2 | Major error |

## Citation

If you use this dataset, please cite:

> He, Y., Wu, M., Deng, S., & Zhang, Y. (2026). *Claim-normalized citation verification (CNCV)* [Data set]. GitHub. https://github.com/IntelligentBibliometrics/CNCV 
