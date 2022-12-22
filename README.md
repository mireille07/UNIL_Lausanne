
# Data Mining & Machines Learning
---
## Project : Detecting the difficulty level of French texts

---
## Group : Lausanne
partcipants: 
  * Mireille Adjaoute 
  *  Lorenzo Corno

## Description : 
As described above in the project 's Title, the main goal of this Kaggle competition is to predict the difficulty level of a french text according to the The Common European Framework of Reference for Languages that describes 6 level of language : A1, A2, B1, B2, C1, C2.

You can find all information and rules on this Kaggle link:[https://www.kaggle.com/t/2607091ee16a4341bf1e8deaeeabab2a]

## Our Youtube Video (Click on the icon)

[![Watch the video](https://2.bp.blogspot.com/-8AHOEYb6eJU/WIlfMd0Kp9I/AAAAAAAAFL0/735baIugAikCCQM-MIAAC038_H6JX2PSwCLcB/s1600/youtube.png)](https://youtu.be/HEMvWrY_owM)


## Dataset Description
- training_data.csv -> the training set (with sentence and respective difficulty)
- unlabelled_test_data.csv -> the test set (with just sentence)
- sample_submission.csv -> a sample submission file in the correct format (with just difficulty)
### Columns
- id: Numerical identifier of the sentence.
- sentence: A sentence in French for which you want to predict the difficulty level.
- difficulty: The difficulty level of the sentence (from A1 to C2). This column would be your target variable.
- oe_difficulty: this is a column obtained by ordinal encoding the data of the difficultty column. Let's precise that we hav'nt really used it at the end.

  We can upload them from github Data folder or you can use directly the Kaggle API and your Kaggle credentials(we will see in the code how to do it).

## Approach
### 1- Installing the necessary packages 
-for language support spacy, nltk 
-for modelling pandas, numpy, sklearn, etc...
### 2- Models
  as Model for our analyses we went for :
  - Logistic regression 
  - KNN
  - Decision tree
  - Random Forest models.


  
  But afterward we notice thatthere were no use for that in our analyses
### 3- Model without cleaning
We implement the models show in class without cleaning. We use a Tf-idf vectorizer and do hyperparameter tuning to find the best hyperparameter and check the results obtained.
### 4- Model with Cleaning data
This time we clean data by: 
- Remove punctuation
- Remove stop word
- Tokenisation
- Lemmatisation
- Vectorization
we did try different approach to see the best combination which lead us not to remove the stop word anymore since some sentences are short.

### Result without Data cleaning : 

|Models                       | Precision     | First Header  | Second Header |First Header|
| --------------------------- | ------------- | ------------- |-------------- |------------|
| Logisitc Regression         | 0.475666      | 0.479224	     | 0.474447      | 0.478125   |
| Random Forest               | 0.416684      | 0.416253	     | 0.401491      | 0.413542   |
| Decision tree Improvement	  | 0.314862      | 0.315516      | 0.311864	     | 0.315625   |
| Decision tree               | 0.301306      | 0.300758      | 0.298111      | 0.301042   |
| KNN Model                   | 0.419700      |	0.354327      | 0.345031      | 0.354167   |






### Result with Data cleaning : 

|Models                       | Precision     | First Header  | Second Header |First Header|
| --------------------------- | ------------- | ------------- |-------------- |------------|
| Logisitc Regression         | 0.501281      | 0.504158	     | 0.499639      | 0.503125   |
| Random Forest               | 0.437922      | 0.420731      | 0.400117      | 0.419792   |
| Decision tree            	  | 0.323231      | 0.315516      | 0.323665      | 0.327083   |
| KNN Model                   | 0.412903      |	0.418594      | 0.408406      | 0.418750   |


### 4- Submission
We use our best model on the cleaned sentence of file 'unlabelled_test_dat.cvs', convert it inthe same format as in the file 'sample_submission.cvs', download in csv format and submit on Kaggle with an accuracy of 0.45.

### 6- Model Improvement:
Many are the ways to improve the accuracy of a model,
in our case , we choose the Principal Component Analysis (PCA) which for some unknown reason didn't improve our model.
then We tried the Bert Model from HuggigngFace...
    
   

