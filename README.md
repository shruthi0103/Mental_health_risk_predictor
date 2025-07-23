# Mental Health Risk Predictor

## Overview

**Mental Health Risk Predictor** is a machine learning-based project designed to identify potential transitions from low-risk to high-risk mental health discussions on Reddit. By analyzing user behavior in subreddits like r/depression, the system aims to predict whether a user might later engage in high-risk communities such as r/SuicideWatch.

This approach supports early intervention strategies, potentially guiding users toward timely mental health support.

---

## Objectives

- Analyze user activity metrics in low-risk mental health communities (e.g., r/depression)
- Identify patterns that correlate with participation in high-risk subreddits (e.g., r/SuicideWatch)
- Build and evaluate predictive machine learning models
- Provide insights for improving online mental health support systems

---

## Dataset

- **Source**: ConvoKit (Reddit comments and posts up to October 2018)
- **Communities Analyzed**:
  - r/depression (Low-risk)
  - r/SuicideWatch (High-risk)
- **User Overlap**: Tracked shared users to study behavioral transitions

---

## Features Extracted

- User ID (anonymized)
- Number of posts and comments
- Word counts (per post/comment and totals)
- Average posting intervals (activity rate)

---

## Models Used

### 🔹 K-Nearest Neighbors (KNN)

- Baseline classifier based on similarity in feature space
- Explored hyperparameters: `k`, distance metric (Euclidean/Manhattan), and weighting
- Limitations: computational cost, data imbalance sensitivity, lower interpretability

### 🔹 Decision Tree

- Tree-based classification with interpretability
- Key features: user activity rate, post count, total word count
- Achieved up to **87.76% accuracy**
- Benefits: clear logic, fast training
- Limitations: overfitting, sensitivity to dataset changes

### 🔹 Random Forest

- Ensemble of decision trees for improved generalization
- Best ROC curve and consistent performance
- Key features: total word count, activity rate, post volume
- Accuracy: **~86.83%**
- Benefits: robustness, lower overfitting risk
- Limitations: interpretability, computational cost

---

## Methodology

1. **Data Cleaning**:
   - Removed moderators, deleted accounts, and empty posts
   - Filtered outliers and spammy activity
2. **Model Training**:
   - 70% training / 30% testing split
   - Hyperparameter tuning for all models
3. **Evaluation**:
   - Confusion matrix
   - ROC curve and AUC
   - Feature importance

---

## Limitations

- Dataset limited to pre-2018 Reddit activity
- Could not detect passive user behavior
- Feature space focused on metadata only (no text semantics)
- User anonymity limits longitudinal tracking
- Data skew: far more users in r/depression than r/SuicideWatch

---

## Future Enhancements

- Introduce **Natural Language Processing (NLP)** for sentiment and content analysis
- Add additional subreddits (e.g., r/anxiety, r/mentalhealth)
- Address class imbalance via stratification or resampling
- Explore deep learning or hybrid modeling techniques

---

## License

This project is intended for academic research and mental health technology exploration. It is not a diagnostic tool and should not be used for clinical decisions.
