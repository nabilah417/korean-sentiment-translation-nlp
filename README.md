# korean-sentiment-translation-nlp
Controlled comparison of Korean-direct and translated-English sentiment classification
# Does Machine Translation Change Korean Sentiment Classification?

Code and experimental materials for NLP Homework 2,
Hanyang University, Fall 2026.

## Research Overview

This study compares two sentiment classification pipelines:

1. KO: Direct classification of Korean movie reviews.
2. KO→EN: Korean-to-English translation followed by classification.

Both pipelines use XLM-R Base with matched review IDs,
sentiment labels, training settings, and random seeds.

## Dataset

Naver Sentiment Movie Corpus (NSMC):
https://github.com/e9t/nsmc

Training: 9,000 reviews
Validation: 1,000 reviews
Testing: 2,000 reviews

## Models

Classification: xlm-roberta-base
Translation: Helsinki-NLP/opus-mt-ko-en

## Reproducing the Experiments

1. Open NLP_HW2_Experiment.ipynb in Google Colab.
2. Select a GPU runtime (Tesla T4 was used).
3. Install the packages specified in the notebook.
4. Mount Google Drive or configure an alternative output directory.
5. Run data preparation and translation.
6. Train both classifiers with seeds 42, 43, and 44.
7. Run statistical evaluation and subgroup analysis.

The notebook saves the selected data splits, translations,
predictions, experiment logs, and result tables.

## Main Results

| Pipeline | Accuracy (%) | Macro-F1 (%) |
|---|---:|---:|
| Korean-direct | 84.47 ± 0.16 | 84.46 ± 0.16 |
| Translated-English | 78.03 ± 0.39 | 78.03 ± 0.39 |

Results are mean ± standard deviation across three seeds.

## Reproducibility Notes

- Data sampling seed: 42
- Model training seeds: 42, 43, 44
- Bootstrap seed: 2026
- Bootstrap resamples: 5,000
- Original dataset: NSMC
- Translation decoding: Beam size 4, no sampling

The manual linguistic subgroup analysis additionally requires
the completed annotation file.

The experiment was run in Google Colab. Fresh-machine
reproduction has not yet been independently verified.
