# RecognAItion

RecognAItion is an experimental repository for audio-based emotion recognition. It gathers several approaches (classical ML and deep learning) and example data processing pipelines to explore emotion classification from speech recordings.

## Project goals

- Collect data preprocessing scripts and feature exports used for training classical ML models.
- Deliver a benchmark accross the two chosen datasets (EmoDB and CremaD) of all the models : K-Nearest Neighbors, Support Vector Machines, Random Forests, and LSTM-based neural networks

## Repository structure

- `KNN/`: K-Nearest Neighbors implementation (`knn.py`).
- `SVM/`: SVM implementation (`svm.py`).
- `Random forest/`: Data and Random Forest model implementations and helpers.
  - `Random forest/models/`: model training/prediction scripts (e.g. `random_final.py`, `random_emo.py`).
  - `Random forest/data/`: datasets, extracted features, and helper CSVs.
- `LSTM/`: LSTM-based models and dataset utilities.
  - `LSTM/own_dataset/`: dataset generator, sample test scripts and pretrained `.pth` model files.
  - `LSTM/CremaD/`, `LSTM/EmoDB/`, `LSTM/EmoDB_and_CremaD_mix/`: dataset-specific model scripts.

## Installation (for Windows)

Create a virtual environment and install dependencies:

```
python -m venv venv
.\venv\Scripts\Activate.ps1
pip install -r requirements.txt
```
For LSTM training/inference, PyTorch and GPU are required.

## Data

You will need to install [EmoDB](https://www.kaggle.com/datasets/piyushagni5/berlin-database-of-emotional-speech-emodb) and [CremaD](https://www.kaggle.com/datasets/ejlok1/cremad)

Additional datasets :
- The `Random forest/data/` folder contains CSV feature exports (many in `filtered_audio_to_csv/`)
- The `LSTM/` contains a data processing pipeline to create a custom dataset

## Warning

You might need to modify the hard-coded path in python scripts to ensure it points ot the right folder

## Results

Here are a few of our results (bold numbers are results found in litterature):

| Modèle           | EMO-DB                 | CREMA D                 |
|------------------|------------------------|-------------------------|
| SVM              | **83** / 79            | **60** / 57             |
| Random Forest    | **84** / 77            | **65** / 54             |
| LSTM             | **90** / 85            | **69** / 57             |
