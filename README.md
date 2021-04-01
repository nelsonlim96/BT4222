# BT4222 Final Project: Hate Speech Classifier

## 1. Problem Statement

With the advent of social media, there has been an increase in the number of cases of hate speech. As Twitter is the most prevalent platform where hate speech is rampant, our group thought it would be interesting to do our final project by creating a machine learning classifier to solve this issue.

## 2. Datasets

Our primary dataset, MMHS150K, is a multimodal dataset that contains 150,000 tweets with images associated with them. However, we will not be using the images as part of our project. The semi-structured data is composed of a Python dict inside a JSON file. There are 150,000 observations (dict entries), 1 per tweet. The key is the tweet ID and there are 3 fields (“img_url”, “tweet_url”, “tweet_text”). “img_url” has a “labels” sub-field while “tweet_url” has a “labels_str” sub-field.

## 3. Hypothesis

### 3.1 Most people tend to use a lot of vulgarities but these are not necessarily hate speech

We aim to test and validate the above by creating a baseline classifier to check if vulgarities are contained in the tweet, and compare this with an advanced classifier which attempts to identify cases which are not hate speech by checking for sarcasm and slang. The difference in the performance of the two models can be used to estimate the number of cases which are misidentified as hate speech.

### 3.2 Hate speech terms such as “Nigga” might be mentioned but it is actually not hate speech

In this case, word sense disambiguation (WSD) can help determine that the term “Nigga” is being used innocuously (i.e. the context and who the Tweet originated from are important). 

### 3.3 Racism in the form of xenophobia is more easily identified than sexism.

This is because xenophobic statements are often paired with certain phrases that allows the model to allocate higher weights to them. For example, a sentence with the words “mexico” and “beaner”, a derogatory term, can be identified as racist simply with the presence of the words. In comparison, sexism tends to be more subtle in real life sentences. For instance, people are less likely to randomly tweet “girls are meant to be in the kitchen” but instead, tweet a sentence with more nuanced sexism or with more context. We are looking to validate this by comparing the performance of the prediction of each of these classes.

## 4. Metholodogy

### 4.1 Pre-processing

- Removing stopwords
- Removing non-English words
- Tokenizing

### 4.2 Modelling

- Base model: Naive Bayes
- Classical ML models: SVM, KNN, Decision Trees, Random Forest, XGB
- Neural networks: LSTM, BERT
