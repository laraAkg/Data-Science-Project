# Heavy-Tail Detection – Data Generation & Model Training

## Project Overview

This project consists of **two Jupyter notebooks** that are used together:

1. **Generate_Data.ipynb**  
   → generates synthetic datasets and visualizations  
2. **Model_Training.ipynb**  
   → trains and evaluates a machine learning model using the generated data  

The goal of the project is to **automatically distinguish between heavy-tailed and non-heavy-tailed distributions** based on diagnostic plots.

---

## Notebooks Overview

### 1️⃣ Generate_Data.ipynb – Data Generation & Visualization

This notebook is responsible for creating the data used in the project.

It:

- generates **synthetic datasets** from different statistical distributions  
  (e.g. Normal, Exponential, Pareto, Student-t, Lognormal)
- automatically assigns a **label** indicating whether a dataset is heavy-tailed
- creates **visual diagnostic plots** for each dataset:
  - Zipf plot  
  - Mean Excess (ME) plot  
  - Exponential Q–Q plot
- generates **augmented versions** of the data (e.g. noise, resampling, scaling)
- saves all outputs in a structured way:
  - raw data files (`.npy`)
  - plots (`.png`)
  - metadata (`.json` and `.csv`)

➡️ **Result:**  
A complete, ready-to-use dataset including plots and metadata for model training.

---

### 2️⃣ Model_Training.ipynb – Model Training & Evaluation

This notebook uses the generated data to train and evaluate a machine learning model.

It:

- loads the generated datasets and plots
- prepares the data for TensorFlow / Keras
- trains a neural network to classify  
  **heavy-tailed vs. non-heavy-tailed distributions**
- applies:
  - cross-validation
  - hyperparameter search (e.g. learning rate, dropout)
  - probability calibration
- automatically selects the **best performing model**
- generates a small **evaluation dashboard** with plots and metrics
- saves:
  - the final trained model
  - a metadata JSON file with all important parameters and results

➡️ **Result:**  
A trained model with transparent evaluation results and reproducible settings.

---

## How to Use the Project (Step by Step)

### 🟢 Requirements

- Google Colab **or** local Jupyter Notebook
- No advanced programming or ML knowledge required

---

### Step 1: Generate the Data

1. Open **Generate_Data.ipynb**
2. Run all cells **from top to bottom**
3. Wait until the notebook finishes execution

➡️ The datasets, plots, and metadata are generated and saved automatically.

---

### Step 2: Train the Model

1. Open **Model_Training.ipynb**
2. Make sure the data paths are correct  
   (default paths are already prepared)
3. Run all cells **in order**
4. At the end:
   - the best model is saved
   - evaluation plots and reports are generated

---

## Who Is This Project For?

- Students in Data Science, Statistics, or Machine Learning
- Anyone interested in understanding heavy-tailed distributions
- Users who want to see a **complete, reproducible ML pipeline**
- Also suitable for **non-expert users** by simply running the notebooks

---

## In Short

- **Generate_Data.ipynb** → creates and visualizes data  
- **Model_Training.ipynb** → learns from the data and evaluates the model  

---

## Generated Plots & Data (Google Drive)

Due to file size constraints, all generated plots and datasets are **not stored directly in this GitHub repository**.

All generated images (Zipf plots, Mean Excess plots, Q–Q plots) and related artifacts are available in the following Google Drive folder:

🔗 https://drive.google.com/drive/folders/1-pF-IUwH5_dcQBodtGM_U-U_e8J0d5rB?usp=sharing

This folder is automatically populated when running `Generate_Data.ipynb` in Google Colab.
