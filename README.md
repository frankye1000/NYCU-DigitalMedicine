# Case_Presentation_1

## Introduction
**Use a doctor’s diagnosis certificate to determine whether the patient is obese.**

* Training data based on textual judgement
Textual judgement: 
	* 200 cases obesity vs. 200 cases unmentioned.
* Testing data based on intuitive judgement
Intuitive judgement: 
	* 200 cases obesity vs. 200 cases absence
* Validation data (50 cases) based on textual judgemen


## Text Preprocessing
* Remove __punctuation__
 * Remove punctuation and numbers to make word split more precise.
* __Word tokenize__
 * The process of splitting a large sample of text into words.
* Remove __stopword__
 * Used to improve the quality of text features or reduce the dimensionality of text features.
* __Lemmatize__
 * Lemmatization is to remove the affixes of the word and extract the main part of the word. 
For example, the word "cars" after lemmatize is "car", and the word "ate" after lemmatize is "eat".

## W2V
* Advantage
 * Compared with one hot encoding, Word to vector can consider a word in the context of the article.
* Algorithm   
 *  word to vector contains two algorithms, Skip-gram and CBOW. 
Skip-gram uses the central word to predict the context, and CBOW uses the context to predict the central word.

![This is a alt text.](https://github.com/frankye1000/NYCU-DigitalMedicine/blob/master/Case_Presentation_1/ppt/W2V.png?raw=true)


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

### Machine Learning
* Naive Bayes
* Random Forest
* SVM

## Result
##### statistic  
| Test data  |  |
| ---------- |:----:|
| Precision  | 0.985|
| Recall     | 0.96 |
| Accuracy   | 0.975|
| f1         | 0.975|

| Validation data |  |
| ---------- |:----:|
| f1         | 0.543|