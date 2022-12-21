
# Data Mining & Machines Learning
---
## Project 2022 : Detecting the difficulty level of French texts
---
## Group : Lausanne
partcipants: Mireille Adjaoute and Lorenzo Corno

## Description : 
As described above in the project 's Title, the main goal of this Kaggle competition is to predict the difficulty level of a french text according to the The Common European Framework of Reference for Languages that describes 6 level of language : A1, A2, B1, B2, C1, C2.

You can find all information and rules on this link:[https://www.kaggle.com/t/2607091ee16a4341bf1e8deaeeabab2a]


## Dataset Description
- training_data.csv -> the training set (with sentence and respective difficulty)
- unlabelled_test_data.csv -> the test set (with just sentence)
- sample_submission.csv -> a sample submission file in the correct format (with just difficulty)
### Columns
- id: Numerical identifier of the sentence.
- sentence: A sentence in French for which you want to predict the difficulty level.
- difficulty: The difficulty level of the sentence (from A1 to C2). This column would be your target variable.

  We can upload them from github Data folder or you can use directly the Kaggle API and your Kaggle credentials(we will see in the code how to do it)

## Approach
### 1) Installing the necessary packages 
-for language support spacy, nltk 
-for modelling pandas, numpy, sklearn...
-if we want to read data into our notebook with the Kaggle API there are some passage to do
### 2) data analysis and preparation
The dataset doesn't have missing value and there are more or less the same number fo elements for each class. We just need to transform the level difficulty to read it, so we encode [difficulty] with an ordinal encoder
  {A1,A2,B1,B2,C1,C2}->{0,1,2,3,4,5}
### 3)Model without cleaning
We implement the models show in class without cleaning. We use a Tf-idf vectorizer and do hyperparameter tuning to find the best hyperparameter and check the results obtained
### 4)Cleaning data
This time we clean data: remove punctuation, tokenisation, lemmatisation\stemming, vectorization
we did try different approach, on the code we delete the bad one and left the best one 
### 5) Submission
We use our best model with the cleaned sentence of file 'unlabelled_test_dat.cvs', then we need to decode our result {0,1,2,3,4,5}->{A1,A2,B1,B2,C1,C2} same format as in the file 'sample_submission.cvs', download in csv format and submit in Kaggle.
