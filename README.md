# Synthetic-Data-Generation
Synthetic Data Generation using LLMs and GMM for healthcare risk prediction.

## Overview
This project investigates whether **synthetic healthcare data** can reliably replace real-world data for training machine learning models. Using **Gaussian Mixture Models (GMM)**, synthetic patient records are generated and evaluated through downstream predictive performance, including **Train-on-Synthetic-Test-on-Real (TSTR)** validation.

The project follows a **data-centric AI approach**, focusing on utility, generalization, and privacy rather than model-only optimization.

---

## Problem Statement
Access to large-scale healthcare datasets is constrained by privacy regulations, data imbalance, and limited availability. While synthetic data is often proposed as a solution, many approaches fail to rigorously validate whether models trained on synthetic data generalize to real patient data.

**Key Question:**  
Can synthetic tabular healthcare data preserve predictive patterns sufficiently to train models that perform well on real-world data?

---

## Research Gaps Addressed
- Lack of downstream-task validation for synthetic data
- Over-reliance on statistical similarity without ML performance testing
- Limited use of **TSTR (Train Synthetic → Test Real)** evaluation
- Insufficient comparison across multiple ML models

---

## Methodology

### 1. Data Preparation
- Real healthcare dataset (~97,000 records, 30 features)
- Target variable: `diagnosed_diabetes`
- Cleaned, encoded, and standardized to ensure schema consistency

### 2. Synthetic Data Generation
- **Gaussian Mixture Model (GMM)**
- Generated 5,000 synthetic patient records
- Preserved feature distributions and correlations

### 3. Model Training Scenarios
- **Real → Real**: Baseline performance on real data
- **Synthetic → Synthetic**: Internal consistency of synthetic data
- **Synthetic → Real (TSTR)**: Generalization capability of synthetic data

### 4. Models Evaluated
- Logistic Regression
- Random Forest
- Gradient Boosting

### 5. Evaluation Metrics
- Accuracy
- Precision
- Recall
- F1-score

---

## Results

### Performance Summary

| Training → Testing | Accuracy |
|-------------------|----------|
| Real → Real (Baseline) | 63.6% |
| Synthetic → Synthetic | 88.0% |
| **Synthetic → Real (TSTR)** | **99.5%** |

### Key Findings
- Models trained on synthetic data generalize exceptionally well to real data
- Synthetic data reduces noise and improves class separability
- Model ranking is preserved across real and synthetic datasets
- Ensemble models show higher robustness than linear models

---

## Why This Matters
- Demonstrates **practical utility** of synthetic data, not just statistical similarity
- Validates synthetic data as a **privacy-preserving alternative** for healthcare ML
- Uses evaluation techniques aligned with **industry and research standards**

---

## Repository Structure

