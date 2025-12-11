# Pitch-Classification-Model

Overview

This project builds several pitch type classifiers using MLB Statcast data. The workflow includes data cleaning, normalization, feature visualization, ANN and KNN models, PCA analysis, and an ensemble model.

Data Preparation

Eight pitch types are used, with each one having a CSV file which is  loaded and processed. Exactly 5000 clean rows are collected from each pitch type. Any row containing missing or invalid values is removed. The datasets are combined into one 40,000 row dataframe.

Normalization

StandardScaler (z-scale) is applied to all numeric pitch features. This produces a fully normalized dataset saved as normalized_pitch_data.csv. Pitch types are encoded using LabelEncoder and one-hot encoding. The dataset is then split into training and testing sets so each pitch type is evenly represented.

Visualization

Features are graphed in a correlation heatmap, and subsequent relationship cluster plots.

KNN Model

A KNN classifier handles tight pitch clusters using distance weighting. This model also ~83% accuracy with K optimized.

ANN Model

The ANN captures interactions between pitch features. This model reaches ~83% accuracy on the test set after being hyperparametrized.

PCA

PCA reduces the five primary features to two principal components. A PCA scatter plot is included to show how pitch types overlap in the reduced space. 

Ensemble Model

The ensemble combines ANN and KNN prediction probabilities using a weighted formula. The model improves decisions on borderline predictions where ANN and KNN disagree.

How to Run

Download the dataset provided here and include it in a folder "/data/." Run the data preparation script to create merged_pitch_data.csv. Use the feature engineering sections for analysis and visualizations. Run the normalization steps to create normalized_pitch_data.csv. Open the main Jupyter notebook. Run preprocessing, then train the ANN, KNN, and PCA models. Run the ensemble model for best accuracy.
