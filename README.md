IMDB Sentiment Analysis using Machine Learning
PROJECT OVERVIEW

This project performs sentiment analysis on movie reviews from the IMDB dataset using Natural Language Processing (NLP) and machine learning models. The goal is to classify reviews as positive or negative by processing raw text and comparing the performance of multiple machine learning classifiers.

The workflow includes:

Data exploration

Text preprocessing

Feature extraction using TF-IDF

Training multiple ML models

Model evaluation and comparison

Visualization of results

DATASET
Dataset used: IMDB Movie Reviews Dataset

The dataset contains 50,000 labeled movie reviews.

Column	Description
review	Text of the movie review
sentiment	Label indicating sentiment (positive / negative)

Example review snippet:

This movie was absolutely amazing. The acting and storytelling were fantastic.

⚙️ Project Workflow
DATA EXPLORATION

Initial dataset analysis includes:

Checking dataset shape

Inspecting columns

Viewing sample rows

Identifying missing values

Calculating review length statistics

A new feature review_length was created to analyze review sizes.

TEXT CLEANING

Raw reviews contain HTML tags, punctuation, and other noise. These were cleaned using regular expressions.

Cleaning steps:

Remove HTML tags

Remove special characters

Convert text to lowercase

Remove extra spaces

Example:

Original:

"This movie <br /> was AMAZING!!!"


Cleaned:

this movie was amazing

TEXT PREPROCESSING

Natural language preprocessing includes:

Tokenization

Stopword removal

Porter stemming

Example:

Original text:

The movie was absolutely wonderful and entertaining


Processed text:

movi absolut wonder entertain

FEATURE EXTRACTION

Text was converted into numerical features using TF-IDF Vectorization.

TfidfVectorizer(max_features=5000)


This creates a 5000-dimensional feature space representing word importance across reviews.

TRAIN-TEST SPLIT

The dataset was split into:

75% training data

25% testing data

train_test_split(test_size=0.25, stratify=y)

MACHINE LEARNING MODELS

The following models were trained and compared:

Traditional ML Models

Logistic Regression

Linear Support Vector Classifier (Linear SVC)

K-Nearest Neighbors (KNN)

Neural Network Models

MLP (100 neurons, ReLU)

MLP (128,64 neurons, tanh)

MLP (256,128,64 neurons, ReLU)

EVALUATION METRICS

Models were evaluated using:

Accuracy

Precision

Recall

F1 Score

Confusion Matrix

The F1-Score was used as the primary evaluation metric since it balances precision and recall.

RESULTS
Model	Accuracy	F1 Score
Logistic Regression	0.8879	0.8892
Linear SVC	~0.882	~0.882
MLP Neural Networks	~0.875 – 0.879	~0.875 – 0.879
KNN	~0.77	~0.77
BEST MODEL

The best performing model was Logistic Regression.

Accuracy: 0.8879
F1 Score: 0.8892


The confusion matrix shows strong performance with most predictions correctly classified.

VISUALIZATIONS

The project includes visualizations for:

Model comparison using F1-Score bar charts

Confusion matrix for the best model

Example visualization:

Model Comparison based on F1 Score

TECHNOLOGIES USED

Python

Pandas

NumPy

NLTK

Scikit-learn

Matplotlib

Seaborn

INSTALLATION

Install required libraries:

pip install pandas numpy nltk scikit-learn seaborn matplotlib


Download NLTK stopwords:

import nltk
nltk.download('stopwords')

HOW TO RUN

1 Place dataset in project directory

IMDB Dataset.csv


2 Run the script:

python sentiment_analysis.py


or open the notebook:

sentiment_analysis.ipynb

 PROJECT STRUCTURE
sentiment-analysis
│
├── sentiment_analysis.ipynb
├── IMDB Dataset.csv
├── README.md
└── results
    ├── confusion_matrix.png
    └── model_comparison.png

FUTURE IMPROVEMENTS

Potential enhancements:

Implement Word2Vec / GloVe embeddings

Apply deep learning models (LSTM / Transformers)

Perform hyperparameter tuning

Deploy as a web application

AUTHOR
Shreya Galurgi
