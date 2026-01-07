# Heavy-Tail Detection – Data Generation, Model Training & Evaluation

## Project Overview

This project demonstrates a **complete and reproducible data science pipeline** for detecting  
**heavy-tailed vs. non-heavy-tailed distributions** based on diagnostic plots.

The project is intentionally designed so that it can also be understood and used by  
**non-expert or non–ML-specialist users** by simply running the notebooks step by step.

It consists of **three Jupyter notebooks**, which are meant to be used together and in order.

---

## Notebooks Overview

### 1️⃣ Generate_Data.ipynb – Data Generation & Visualization

This notebook is responsible for creating the data used in the project.

It:

- generates **synthetic datasets** from different statistical distributions  
  (e.g. Normal, Exponential, Pareto, Student-t, Lognormal)
- automatically assigns a **label** indicating whether a dataset is heavy-tailed
- creates **diagnostic plots** for each dataset:
  - Zipf plot  
  - Mean Excess (ME) plot  
  - Exponential Q–Q plot
- generates **augmented variants** of each dataset (noise, resampling, scaling)
- stores all outputs in a structured way:
  - raw data (`.npy`)
  - plots (`.png`)
  - metadata (`.json` and `.csv`)

**Result:**  
A complete dataset with plots and metadata, ready for model training.

---

### 2️⃣ Model_Training.ipynb – Model Training & Selection

This notebook trains a neural network using the generated plots.

It:

- loads the generated plots and metadata
- prepares image-based inputs for TensorFlow / Keras
- trains a CNN to classify  
  **heavy-tailed vs. non-heavy-tailed distributions**
- performs:
  - cross-validation
  - hyperparameter tuning (e.g. learning rate, dropout)
  - probability calibration
- automatically selects the **best performing model**
- generates evaluation plots and metrics
- saves:
  - the final trained model
  - a metadata file containing thresholds, calibration parameters, and CV results

**Result:**  
A trained, calibrated model with reproducible and transparent evaluation results.

---

### 3️⃣ Model_Evaluation.ipynb – Model Evaluation & Explainability

This notebook is used **after training** to analyze and apply the best model.

It:

- reloads the best trained model and its metadata
- reconstructs the original cross-validation splits
- summarizes model performance on:
  - training
  - validation
  - test data
- visualizes performance metrics (accuracy, ROC-AUC, etc.)
- applies **Grad-CAM** to explain which plot regions influence the model’s decisions
- allows evaluation of **real-world time series data**:
  - CSV upload
  - automatic plot generation
  - prediction of heavy-tail probabilities
- exports predictions and evaluation plots

**Result:**  
A transparent, explainable evaluation of the trained model, including support for real data.

---

## How to Use the Project (Step by Step)

### Requirements

- Google Colab **or** local Jupyter Notebook
- No advanced machine learning knowledge required

---

### Step 1: Generate the Data

1. Open **Generate_Data.ipynb**
2. Run all cells from top to bottom
3. Wait until execution finishes

All datasets, plots, and metadata are generated automatically.

---

### Step 2: Train the Model

1. Open **Model_Training.ipynb**
2. Ensure the default paths are unchanged
3. Run all cells in order

At the end:
- the best model is saved
- evaluation reports are created

---

### Step 3: Evaluate & Apply the Model

1. Open **Model_Evaluation.ipynb**
2. Run all cells from top to bottom
3. Optional:
   - upload your own CSV time series
   - evaluate real-world data
   - inspect Grad-CAM visual explanations

---

## Who Is This Project For?

- Students in Data Science, Statistics, or Machine Learning
- Anyone interested in heavy-tailed distributions
- Users who want to see a **complete end-to-end ML workflow**

---

## In Short

- **Generate_Data.ipynb** → creates and visualizes datasets  
- **Model_Training.ipynb** → trains and selects the best model  
- **Model_Evaluation.ipynb** → evaluates, explains, and applies the model  

---

## Generated Plots & Data (Google Drive)

Due to file size constraints, generated plots and datasets are **not stored directly in this repository**.

All generated images and artifacts are available in the following Google Drive folder:

[https://drive.google.com/drive/folders/1-pF-IUwH5_dcQBodtGM_U-U_e8J0d5rB?usp=sharing](https://drive.google.com/drive/folders/1-pF-lUwH5_dcQBodtGM_U-U_e8J0d5rB?usp=drive_link)

This folder is automatically populated when running `Generate_Data.ipynb` in Google Colab.
