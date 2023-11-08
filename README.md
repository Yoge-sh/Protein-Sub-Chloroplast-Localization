# Protein-Sub-Chloroplast-Localization
Multiclass Protein Sub-Chloroplast Localization with Ensemble Neural Networks, Feature Engineering and advanced NLP techniques.

## Project Overview

This GitHub repository contains the code and resources for a multiclass classification project focused on predicting the sub-chloroplast localization of proteins within a cell. The project leverages state-of-the-art techniques in bioinformatics and machine learning to classify proteins into five different sub-chloroplast regions: Lumen, Envelope, Thylakoid, Plastoglobule, and Stroma. The goal is to determine whether a given protein is present in a particular location or not.

## Dataset

The project uses a benchmark and novel dataset that includes protein structure information in the form of amino acid chains. Each protein in the dataset is associated with a binary value representing its presence or absence in one of the five sub-chloroplast locations. This dataset serves as the foundation for the model training and evaluation.

## Feature Engineering

In the feature engineering phase, we utilize evolutionary profiles such as Hidden Markov Models (HMM) and Position-Specific Scoring Matrices (PSSM) for each protein. These profiles are used to create new features for protein classification. Additionally, we employ two word embedding techniques, Word2Vec and Fasttext, to transform protein sequences into 2D arrays or matrices.

A unique contribution of this project is the application of the SkipXGram technique to generate Skip5gram-bigram vectors for HMM matrices, PSSM matrices, and the original protein sequence. These vectors play a crucial role in our classification model.

## Multiclass Classification

To predict the sub-chloroplast localization of proteins, we develop separate artificial neural network (ANN) models for each of the five classes (Lumen, Envelope, Thylakoid, Plastoglobule, and Stroma). Each ANN model takes as input a feature vector that combines:

1. Word embedding vectors from FastText and Word2Vec (each of length 400).
2. Skip5gram-bigram vectors for HMM and PSSM protein sequences (each of length 400).
3. Skip5gram vectors of the original protein sequence (of length 400).
4. Monogram vector derived from the protein sequence (of length 20).
## Model Structure


<img width="792" alt="image" src="https://github.com/Yoge-sh/Protein-Sub-Chloroplast-Localization/assets/93325653/f2e026f1-f225-4473-aee6-c0245f889d6e">

## Model Ensemble

After training individual models for each class, we ensemble the results to make the final prediction. This approach aims to capture the nuances of protein localization in different sub-chloroplast regions.

## Model Evaluation

We evaluate the performance of our models on a test dataset that represents 20% of the entire dataset. The strict accuracy on the test dataset is 60%, while the overall dataset achieves an accuracy of 92%. For a more relaxed accuracy measure, we achieve 88.45% on the test dataset and an impressive 97.68% on the entire dataset.

## Results
 
### Strict Accuracies for Benchmark and Novel Dataset
| Dataset  | Test Accuracy | Overall Dataset Accuracy
| ------------- | ------------- |  ------------- |
| Benchmark Dataset  | 0.6121  |   0.9221        |
| Novel Dataset  | 0.6  |     0.9173      |

### Relax Accuracies for Benchmark and Novel Dataset
| Dataset  | Test Accuracy | Overall Dataset Accuracy
| ------------- | ------------- |  ------------- |
| Benchmark Dataset  | 0.8845  |   0.9768      |
| Novel Dataset  | 0.896  |     0.9785      |
 
## Repository Contents

This repository includes:
- The separate notebooks for the Benchmark dataset and Novel dataset
- Code for data preprocessing, feature engineering, model training, and evaluation.
- Documentation and notebooks for understanding the project workflow.
