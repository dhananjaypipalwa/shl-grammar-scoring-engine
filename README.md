# SHL Grammar Scoring Engine

Machine learning solution for the SHL Hiring Assessment 2026.

## Problem Statement

The objective is to predict the grammar quality score of spoken English audio samples on a continuous scale from 0 to 5.

The dataset contains 769 labeled training audio samples and 216 test audio samples.

## Approach

The problem is formulated as a regression task.

### Pipeline

Audio → Preprocessing → Acoustic Feature Extraction → Extra Trees Regression → Grammar Score

### Audio Features

The following features were extracted:

- MFCC
- Delta MFCC
- Spectral Centroid
- Spectral Bandwidth
- Spectral Rolloff
- Zero-Crossing Rate
- RMS Energy
- Chroma Features
- Audio Duration
- Amplitude Statistics

Audio was loaded as mono at 16 kHz and leading/trailing silence was removed.

## Model

An Extra Trees Regressor was used because it can capture nonlinear relationships and works effectively with a relatively small tabular feature set.

## Results

| Metric | Score |
|---|---:|
| Training RMSE | 0.0770 |
| Validation RMSE | 0.6995 |
| Validation Pearson Correlation | 0.8585 |
| Kaggle Public Score | 0.7069 |

## Files

- `notebook55d9741d54.ipynb` — Complete Kaggle notebook containing preprocessing, feature extraction, training and evaluation.
- `submission.csv` — Final predictions for the 216 test samples.

## Kaggle Submission

The final submission achieved a public leaderboard score of **0.7069**.
