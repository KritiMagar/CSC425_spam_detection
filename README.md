# CSC 425 Term Project: SMS Spam Detection

A practical machine learning project evaluating text classifiers to automatically filter spam messages.

---

## 1. Team Member Information
* **Name:** Kriti
* **Project Type:** Individual Project
* **Course:** CSC 425 – Artificial Intelligence

I am responsible for the full pipeline: data preprocessing, building and tuning the models, tracking experiments, and completing all project milestones and reports.

---

## 2. Project Description
The goal of this project is to build an AI text classifier that takes an incoming SMS message and predicts whether it is:
* **Ham:** A legitimate, personal message
* **Spam:** Unsolicited advertising, scam, or phishing attempt

Spam messages waste time and pose security risks. The challenge here is not just achieving high overall accuracy, but ensuring high precision so legitimate personal texts are never falsely marked as spam.

### Approach
1. **Feature Extraction:** Convert raw text into numerical feature vectors using `TfidfVectorizer`.
2. **Baseline Model:** Multinomial Naive Bayes.
3. **Comparison Model:** Logistic Regression.
4. **Evaluation:** Compare models using accuracy, precision, recall, and confusion matrices.

---

## 3. Dataset & Resources
* **Dataset Name:** SMS Spam Collection Dataset
* **Source:** UCI Machine Learning Repository / Kaggle
* **Size:** 5,574 labeled English SMS messages
  * **Ham:** 4,825 messages (~86.6%)
  * **Spam:** 747 messages (~13.4%)
* **Key Tools:** Python, Google Colab, Scikit-learn, Pandas

---
## 4. Milestone 2: Data Preprocessing & Baseline Prototype

* **Dataset**: Cleaned UCI SMS Spam Collection (5,171 unique messages after dropping 403 duplicates).
* **Preprocessing**: Stratified 80/20 train/test split, lowercasing, English stop words removal, and TF-IDF vectorization (max 3,000 features)
* **Models Evaluated**:
  * `DummyClassifier` (baseline floor): 87.33% Accuracy, 0.00% F1-score
  * `MultinomialNB` (working prototype): 97.39% Accuracy, 100.00% Precision, 79.39% Recall, 88.51% F1-score
* **Key Findings**: Zero false positives on test data (100% precision); full pipeline verified end-to-end on sample messages.

  ---
## 5. Milestone 3: Logistic Regression & Threshold Tuning

- **Model & Tuning**: Trained `LogisticRegression` on the 3,000 TF-IDF features and swept probability thresholds from 0.50 down to 0.20.
- **Results**:
  - `LogisticRegression` (Default 0.50): 95.94% Accuracy, 97.85% Precision, 69.47% Recall, 81.25% F1-score[cite: 10]
  - `LogisticRegression` (Tuned 0.25): 97.39% Accuracy, 91.94% Precision, 87.02% Recall, 89.41% F1-score[cite: 10]
- **Key Findings**: Lowering the cutoff to 0.25 fixed low spam probability scores caused by class imbalance, catching 114/131 spam messages (12 more than Naive Bayes) while keeping false positives low (10/903 ham).
