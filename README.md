# ENGG2112 — Cross-lake bloom forecasting

This project investigates whether models trained on several lakes
can predict bloom conditions at an unseen lake.

## Models
- Environmental multilayer perceptron (MLP)
- Combined environmental MLP and satellite-image CNN
- Baselines and control experiments

## Evaluation
Leave-one-lake-out evaluation across Erie, Okeechobee,
Champlain and Upper Klamath.

## Reading the results
Open results/team_findings/OPEN_ME_results.html in a browser.
The notebooks also contain code and saved outputs.

## Environment
Python notebooks in VS Code on Ubuntu.
Package versions are listed in requirements.txt.

## Data
Datasets, satellite images and trained model weights are excluded
from this repository and must be shared separately to rerun the code.
Some notebooks currently use local file paths that require updating
on another computer.