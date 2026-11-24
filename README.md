## Overview
This repository contains an exploratory data analysis (EDA) of the Red Wine Quality dataset, comprising 1,599 samples across 12 attributes. The objective of this project is to apply foundational linear algebra and probability concepts—specifically vector extraction, covariance estimation, eigendecomposition, and distribution profiling—to examine structural variance and feature behavior.

## Repository Structure
* `winequality-red.csv` — Primary dataset 
* `assignment4.ipynb` — Jupyter Notebook file with statistical distribution analysis.
* `README.md` — Project documentation and analytical summary.


## Tech Stack
* **Language:** Python
* **Libraries:** `NumPy`, `Pandas`, `Matplotlib`, `Seaborn`


## Analytical Workflow & Key Findings

### 1. Data Loading & Integrity Verification
The dataset was loaded into a Pandas DataFrame and inspected consistency. All 1,599 records across the 12 columns were verified to contain zero missing values, requiring no mean imputation.

### 2. Feature Vector Extraction
Individual chemical attributes (`alcohol` and `citric acid`) were isolated as one-dimensional NumPy arrays to represent feature columns as discrete vectors.

### 3. Covariance Matrix Estimation
A feature matrix (`X`) was constructed using `pH` and `quality`, and its sample covariance matrix was computed via `np.cov(X.T)`. The resulting matrix revealed minimal linear co-variation between `pH` and `quality`, indicating that the two attributes vary largely independently of one another.

### 4. Eigendecomposition & Geometric Interpretation
Eigendecomposition (`np.linalg.eig`) was performed on the covariance matrix to identify the principal axes of variation:
* **Eigenvectors:** The eigenvectors align closely with the original coordinate axes (`pH` and `quality`)
* **Eigenvalues:**  data cloud forms an elongated, narrow distribution—tightly concentrated along `pH` and comparatively dispersed along `quality`.

### 5. Distribution Analysis (`quality`)
Statistical profiling and histogram visualization were conducted on the `quality` target variable:
* **Central Tendency:** The modal rating is 5, with the mean and median clustered closely around average quality scores.
* **Dispersion & Shape:** The standard deviation indicates moderate concentration around the mean. Skewness and excess kurtosis metrics show a nearly symmetric distribution with a slight positive skew and moderately heavier tails than a standard normal curve.
