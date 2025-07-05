# Amazon Review Sentiment Analysis

## 🧠 Problem Statement
Given Amazon product reviews, can we automatically predict whether the sentiment of a review is **positive** or **negative**?

## 📁 Dataset
**Note: The dataset Reviews.csv is too large for GitHub and has been excluded. Please download it from Kaggle and place it in the data/ directory manually.**

- Size: ~568,000 reviews
- Source: Amazon Fine Food Reviews (Kaggle)
- Fields Used: `Text`, `Score`
- Converted into Sentiment Labels:
  - Score ≥ 4 → Positive
  - Score ≤ 2 → Negative
  - Score == 3 → Neutral (removed)

## 🔧 Tools Used
- pandas: data loading & manipulation
- nltk: stopword removal
- re: text preprocessing
- sklearn:
  - TfidfVectorizer: convert text to features
  - train_test_split: create training/testing sets
  - LogisticRegression / Naive Bayes: model training
  - accuracy_score, classification_report: evaluation

## 🧹 Step-by-Step Workflow
1. **Load and inspect the dataset**
2. **Drop neutral reviews**
3. **Clean the text**: lowercasing, remove punctuation, digits, stopwords
4. **Convert to numerical** using TF-IDF (`max_features=5000`)
5. **Split data** into training and test sets (80/20)
6. **Train the model** using Logistic Regression
7. **Evaluate** using accuracy and F1-score

## ✅ Final Model Performance
- Model: `LogisticRegression(max_iter=200)`
- Accuracy: **90.17%**
- Vectorizer: `TfidfVectorizer(max_features=5000)`
- Dataset size after cleaning: ~525,000 samples