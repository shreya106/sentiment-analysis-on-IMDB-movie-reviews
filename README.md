**IMDB Sentiment Analysis using Machine Learning**


**PROJECT OVERVIEW**

This project performs sentiment analysis on movie reviews from the IMDB dataset using Natural Language Processing (NLP) and machine learning models. The goal is to classify reviews as positive or negative by processing raw text and comparing the performance of multiple machine learning classifiers.



**The workflow includes:**

1. Data exploration

2. Text preprocessing

3. Feature extraction using TF-IDF

4. Training multiple ML models

5. Model evaluation and comparison

6. Visualization of results

**DATASET**

-Dataset used: IMDB Movie Reviews Dataset

-The dataset contains 50,000 labeled movie reviews.

Column	Description:
1. review	Text of the movie review
 
2. sentiment	Label indicating sentiment (positive / negative)

Example review snippet:

  This movie was absolutely amazing. The acting and storytelling were fantastic.

Project Workflow:-

**DATA EXPLORATION**

 Initial dataset analysis includes:

 1. Checking dataset shape

 2. Inspecting columns

 3. Viewing sample rows

 4. Identifying missing values

 5. Calculating review length statistics

A new feature review_length was created to analyze review sizes.

**TEXT CLEANING**

Raw reviews contain HTML tags, punctuation, and other noise. These were cleaned using regular expressions.

Cleaning steps:

 1. Remove HTML tags

 2. Remove special characters

 3. Convert text to lowercase

 4. Remove extra spaces

**Example:**

Original:

"This movie <br /> was AMAZING!!!"


Cleaned:

this movie was amazing

**TEXT PREPROCESSING**

Natural language preprocessing includes:

1. Tokenization

2. Stopword removal

3. Porter stemming

Example:

Original text:

The movie was absolutely wonderful and entertaining


Processed text:

movi absolut wonder entertain

**FEATURE EXTRACTION**

Text was converted into numerical features using TF-IDF Vectorization.

TfidfVectorizer(max_features=5000)


This creates a 5000-dimensional feature space representing word importance across reviews.

**TRAIN-TEST SPLIT**

The dataset was split into:

75% training data

25% testing data

train_test_split(test_size=0.25, stratify=y)

**MACHINE LEARNING MODELS**

The following models were trained and compared:

 Traditional ML Models

 Logistic Regression

 Linear Support Vector Classifier (Linear SVC)

 K-Nearest Neighbors (KNN)

 Neural Network Models

 MLP (100 neurons, ReLU)

 MLP (128,64 neurons, tanh)

 MLP (256,128,64 neurons, ReLU)

**EVALUATION METRICS**

Models were evaluated using:

 Accuracy

 Precision

 Recall

 F1 Score

 Confusion Matrix

The F1-Score was used as the primary evaluation metric since it balances precision and recall.

RESULTS

Model  	Accuracy	 F1  Score

Logistic  Regression	 0.8879	 0.8892

Linear SVC	~0.882	~0.882

MLP Neural Networks	~0.875 – 0.879	~0.875 – 0.879

KNN	~0.77	~0.77

**BEST MODEL**

The best performing model was Logistic Regression.

Accuracy: 0.8879
F1 Score: 0.8892


The confusion matrix shows strong performance with most predictions correctly classified.

VISUALIZATIONS
![model comparison](Models_Comparison)
![Best Performing model](Best_Performing_model)

**TECHNOLOGIES USED**

Python

Pandas

NumPy

NLTK

Scikit-learn

Matplotlib

Seaborn

**INSTALLATION**

Install required libraries:

pip install pandas numpy nltk scikit-learn seaborn matplotlib


Download NLTK stopwords:

import nltk
nltk.download('stopwords')

**HOW TO RUN**

 1. Place dataset in project directory

      IMDB Dataset.csv


 2. Run the script:

python sentiment_analysis.py

**AUTHOR**

Shreya Galurgi
