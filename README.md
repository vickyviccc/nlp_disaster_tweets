# nlp_disaster_tweets
This project is a submission for the Kaggle Natural Language Processing with Disaster Tweets competition. The goal is to build a machine learning model that classifies tweets as indicating a real disaster or not.


Table of Contents
Project Overview
Data
Feature Engineering
Models Used
Ensemble Approach
Usage
Results


Project Overview:
This project tackles a binary text classification problem, predicting whether a tweet is related to a disaster. The challenge lies in understanding the nuances in language that differentiate real disaster-related tweets from unrelated ones, despite similar keywords.

Data
The dataset contains:

id: Unique identifier for each tweet.
keyword: A keyword from the tweet.
location: The tweet's location.
text: The tweet content.
target: Label indicating whether a tweet is about a real disaster (1) or not (0).
The dataset is split into:

train.csv: For training and validating models.
test.csv: For generating predictions for Kaggle submission.

Feature Engineering
Text Cleaning: Removal of URLs, mentions, punctuation, and conversion to lowercase.
TF-IDF Transformation: Used to vectorize the cleaned text for better feature representation.
One-Hot Encoding: Applied to keyword and location fields to capture categorical information.
Text Length: Added as a feature, capturing the length of each tweet.
Sentiment Analysis: Used VADER to compute sentiment scores, providing insight into tweet sentiment.

Models Used
The project explored multiple models, including:
Logistic Regression with TF-IDF features.
CatBoost for gradient boosting, with custom depth and learning rate.
XGBoost for tree-based learning to capture structured data patterns.
Voting Classifier (Ensemble) with optimized weights for each base model to maximize accuracy.

Ensemble Approach
A weighted voting ensemble was used to combine the predictions from Logistic Regression, CatBoost, and XGBoost. Each model was tuned individually, with Logistic Regression having a higher weight due to its consistent performance on text features. The ensemble was optimized using Grid Search to select the best model weights.

The ensemble model achieved:

Validation Accuracy: Approximately 0.79–0.80 depending on the fine-tuning parameters.
Classification Metrics: Precision, Recall, and F1-score for both disaster and non-disaster classes were measured to ensure balanced performance.

Future Improvements
Advanced NLP Models: Experiment with deep learning NLP models, like BERT, to improve text classification accuracy.
Feature Engineering: Explore additional features such as word embeddings or location-based insights.
Hyperparameter Tuning: Further optimize parameters in CatBoost and XGBoost to explore higher model depths and learning rate schedules.
