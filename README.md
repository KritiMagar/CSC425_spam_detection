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
