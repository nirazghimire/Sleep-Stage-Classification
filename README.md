# Sleep Stage Classification from Raw EEG Data

This repository contains a machine learning project focused on the automatic classification of sleep stages using raw electroencephalography (EEG) data. The goal is to replicate the work of a sleep technologist by building a model that can accurately distinguish between different phases of sleep (e.g., Wake, REM, N1, N2, N3/4) from neurophysiological signals.

<p align="center">
  </p>

## 🚀 Project Overview

This project implements a complete end-to-end pipeline for a classic problem in computational neuroscience and sleep medicine. The process involves loading raw, multi-channel EEG data in the European Data Format (.edf), preprocessing and epoching the data, engineering robust features based on frequency bands, and training a classifier to predict the corresponding sleep stage for each epoch.

## ✨ Key Features

* **Data Handling:** Processes raw, annotated sleep data directly from `.edf` files using the `mne-python` library.
* **Signal Processing:** Segments continuous EEG signals into 30-second epochs, which is the standard for sleep scoring.
* **Advanced Feature Engineering:** Extracts meaningful features by calculating the relative power spectral density (PSD) across five critical neurological frequency bands:
    * **Delta** (0.5-4.5 Hz)
    * **Theta** (4.5-8.5 Hz)
    * **Alpha** (8.5-11.5 Hz)
    * **Sigma** (11.5-15.5 Hz)
    * **Beta** (15.5-30 Hz)
* **Machine Learning Pipeline:** Utilizes a `scikit-learn` pipeline that integrates the feature extraction step directly with the model, ensuring a streamlined and reproducible workflow.
* **Model:** Employs a `RandomForestClassifier` to effectively learn the complex patterns associated with different sleep stages.

## 🛠️ Tech Stack

* **Python**
* **MNE-Python:** The core library for processing EEG/MEG data.
* **Scikit-learn:** Used for building the machine learning pipeline, model training, and evaluation.
* **NumPy & Pandas:** For numerical operations and data manipulation.
* **Matplotlib:** For data visualization.
* **Joblib:** For saving the final trained model pipeline.

## ⚙️ Usage

The main workflow is contained within the Jupyter Notebook. To use the project:

1.  Ensure you have the required `.edf` data files (raw signals and annotations).
2.  Install the necessary libraries from `requirements.txt`.
3.  Run the cells in the notebook sequentially to load data, preprocess, train the model, and evaluate its performance.
4.  The final, trained pipeline is saved to `model.joblib` and can be loaded for inference on new data.
