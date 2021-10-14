

DIGITAL

MEDICINE

CASE1:

OBESITY DETECTION

GROUP3

葉詠富 310554031

游智鈞 待填

高承翰 待填





CONTENTS

**01 Introduction**

**02 Text Preprocessing**

**03 Method**

**04 Result**





01 INTRODCUTION





TARGET AND DATASET

Target

Use a doctor ’s diagnosis certificate to determine whether the patient is obese.

Train/Test Dataset

\1. Training data based on textual judgement

• Textual judgement: 200 cases obesity vs. 200 cases unmentioned.

\2. Testing data based on intuitive judgement

• Intuitive judgement: 200 cases obesity vs. 200 cases absence

Validation Dataset

Validation data (50 cases) based on textual judgement





D ATA PIPELINE

Train

Statistic &

weight

Clear

Validatio

n

Text

preprocessing

Datase

Test

W2V

result

t

Naïve Bayes

Random Forest

SVM

Validatio

n





02 TEX T PREPRECESSING





TEXT CLEAR

a. Remove punctuation

Remove punctuation and numbers to make word split more precise.

b. Word tokenize

The process of splitting a large sample of text into words.

c. Remove stopword

Used to improve the quality of text features or reduce the dimensionality of text features.

d. Lemmatize

Lemmatization is to remove the affixes of the word and extract the main part of the word.

For example, the word "cars" after lemmatize is "car", and the word "ate" after lemmatize is "eat".





W2V

a. Advantage

Compared with one hot encoding, Word to vector can consider a word in the context of the article.

b. Algorithm

word to vector contains two algorithms, **Skip-gram** and **CBOW**.

Skip-gram uses the central word to predict the context, and CBOW uses the context to predict the central word.

**input**

**projection**

**output**

**input**

**projection**

**output**

**w(t-2)**

**w(t-1)**

**w(t-2)**

**w(t-1)**

**w(t)**

**w(t)**

**w(t+1)**

**w(t+2)**

**w(t+1)**

**w(t+2)**

**Skip-gram**

**CBOW**





03 METHOD





STATISTIC

a. Most similar

Use cosine to calculate the angle and find the most similar word of “obesity” and “obese”.

b. Weight

\1. obesity and obese are key words for obesity, so 50 points

obesity

morbid

asthma

htn

are given for evaluation.

\2. Morbidly, morbid, hyperlipidemia and obesity-related

words are the most similar.

\3. Asthma and htn are not so close, so give a weight of 20

points.

hyperlipidemi

a

obese

50

morbidly

28

c. Criterion

Count the weight of an article, weight greater than 50

points is obesity.

weight

20





MACHINE LEARNING

Naïve Bayes

使用機器學習演算法，這邊簡單介紹

Random Forest

使用機器學習演算法，這邊簡單介紹 待完成

SVM





04 RESULT





STATISTIC RESULT

a. Test dataset

Precision

0.989

0.96

Recall

Accuracy

f1

0.975

0.975

b. Validation

Precision

Recall

Accuracy

f1

0.543





MACHINE LEARNING RESULT

Naïve Bayes

Random Forest

SVM

a. Test dataset

Precision

Recall

Accuracy

f1

待完成

Precision

Precision

Recall

Accuracy

f1

Recall

Accuracy

f1

b. Validation

f1

f1

f1





THANK YO U





GITHUB





REFERENCE





REFERENCE

[1]python 去除所有的中文 英文标点符号(<https://blog.csdn.net/weixin_38819889/article/details/105389248>)

[2]Python處理中文標點符號大集合

(https://codertw.com/%E7%A8%8B%E5%BC%8F%E8%AA%9E%E8%A8%80/356827/)

[3]英文自然語言處理的經典工具 NLTK([https://clay-atlas.com/blog/2019/07/30/nlp-python-cn-nltk-kit](https://clay-atlas.com/blog/2019/07/30/nlp-python-cn-nltk-kit/)[/](https://clay-atlas.com/blog/2019/07/30/nlp-python-cn-nltk-kit/)[)](https://clay-atlas.com/blog/2019/07/30/nlp-python-cn-nltk-kit/)

[4] Word2Vec的参数解释(<https://blog.csdn.net/laobai1015/article/details/86540813>)

[5] [NLP入门（三）词形还原（Lemmatization）](https://www.cnblogs.com/jclian91/p/9898511.html)(https://www.cnblogs.com/jclian91/p/9898511.html)

[6] Word2Vec的簡易教學與參數調整指南(<https://www.kaggle.com/jerrykuo7727/word2vec>)

[7]新手村逃脫！初心者的 Python 機器學習攻略 1.0.0 documentation([https://yaojenkuo.io/ml-newbies/07-](https://yaojenkuo.io/ml-newbies/07-performance.html)

[performance.html](https://yaojenkuo.io/ml-newbies/07-performance.html))

[8] Word2vec from scratch (Skip-gram & CBOW)(https://medium.com/@pocheng0118/word2vec-from-scratch-skip-

gram-cbow-98fd17385945)





CONTRIBUTION OF

GROUP MEMBERS





CONTRIBUTE

Name

葉詠富

Responsible

\1. Data clear

\2. Word to vector

\3. Try Statistic method

\4. PPT design

游智鈞

高承翰

