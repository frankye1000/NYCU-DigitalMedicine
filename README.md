﻿# Case_Presentation_1

## Introduction
**Use a doctor’s diagnosis certificate to determine whether the patient is obese.**

* Training data based on textual judgement
Textual judgement: 
	* 200 cases obesity vs. 200 cases unmentioned.
* Testing data based on intuitive judgement
Intuitive judgement: 
	* 200 cases obesity vs. 200 cases absence
* Validation data (50 cases) based on textual judgemen


## Data Pipeline
![Data Pipeline](https://github.com/frankye1000/NYCU-DigitalMedicine/blob/master/Case_Presentation_1/ppt/datapipeline.PNG?raw=true)



## Text Preprocessing
* Remove __punctuation__
	* Remove punctuation and numbers to make word split more precise.
* __Word tokenize__
	* The process of splitting a large sample of text into words.
* Remove __stopword__
	* Used to improve the quality of text features or reduce the dimensionality of text features.
* __Lemmatize__
	* Lemmatization is to remove the affixes of the word and extract the main part of the word. For example, the word "cars" after lemmatize is "car", and the word "ate" after lemmatize is "eat".



## W2V
* Advantage
	* Compared with one hot encoding, Word to vector can consider a word in the context of the article.
* Algorithm   
	*  word to vector contains two algorithms, Skip-gram and CBOW. Skip-gram uses the central word to predict the context, and CBOW uses the context to predict the central word.

![w2v](https://github.com/frankye1000/NYCU-DigitalMedicine/blob/master/Case_Presentation_1/ppt/W2V.png?raw=true)


## Method
### Statistic
* Most similar
	* Use cosine to calculate the __angle__ and find the most similar word of __obesity__ and __obese__.
* Weight
	* obesity and obese are key words for obesity, so 50 points are given for evaluation. 
	* Morbidly, morbid, hyperlipidemia and obesity-related words are the most similar.
	* Asthma and htn are not so close, so give a weight of 20 points.
* Criterion 
	* Count the weight of an article, weight greater than 50 points is obesity.

### Machine learning article vector
* A、 Calculate the average vector of the article and use it as the article vector.
* B、 Calculate the weight vector of the article, give the weight to the key words, and use it as the article vector.



### Machine Learning Classification algorithm
* Naive Bayes
	* Naive bayes is a classification model based on calculating the probability of conditions. By assuming that each event is independent, the probability under each condition can be calculated to obtain the probability of the event (category) occurring
* Random Forest
	* The (random forest) algorithm establishes the outcome based on the predictions of the decision trees. It predicts by taking the average or mean of the output from various trees. Increasing the number of trees increases the precision of the outcome.
* XGboost
	* XGBoost (Extreme Gradient Boosting) is a Gradient Boosted Tree (GBDT) that keeps the original model unchanged every time, and adds a new function to the model to correct the error of the previous tree to improve the overall model. Mainly used to solve the problem of supervision is learning, can be used for classification can also be used for regression problems.


## Result
#### statistic  
| Test data  |  |
| ---------- |:----:|
| Precision  | 0.985|
| Recall     | 0.96 |
| Accuracy   | 0.975|
| f1         | 0.975|

| Validation data |  |
| ---------- |:----:|
| f1         | 0.543|


#### Machine learning(A)
| Test data  | Naive Bayes| Random Forest| XGBoost  |
| ---------- |:----------:|:------------:|:--------:|
| Precision  | 0.70       | 0.72         | 0.73     |
| Recall     | 0.63       | 0.68         | 0.73     |
| Accuracy   | 0.70       | 0.73         | 0.75     |
| f1         | 0.66       | 0.70         | 0.73     |

| Validation data | Naive Bayes| Random Forest| XGBoost    |
| ----------      |:----------:|:------------:|:----------:|
| f1              | 0.543      |   0.485      | 0.514      |