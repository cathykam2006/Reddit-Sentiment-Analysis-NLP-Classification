# Project 3 - Sentiment Analysis + Reddit Classification

## 1. Problem Statement:
</br>
As a data scientist and a linguist, I would like to help marketers and game manufacturers to better promote the pokemon franchise as well as Reddit to automate their post classification process. Therefore, this project aims to (1) identify the keywords that could act as a major classifier to distingish r/pokemon from r/pokemontrade; (2) users' interest and sentiment and (3) create a model that could classify the posts effectively based on the keywords.

## Process:
First, to **use Pushshift's API as a form of webscraping to collect posts from two subreddits**. 
</br>
Meanwhile, a sentiment and keyword analysis will then be conducted as part of the exploratory data analysis (EDA).
</br>
Then, Natural Language Processing will be applied to train a classifier to distinguish which subreddit a given post came from, which is considered as a binary classification problem. 

---

# Project Structure:
1. Problem Statement
2. Data Collection
3. Data Cleaning & EDA
4. Preprocessing & Modeling
5. Evaluation and COnceptual Understanding
6. Conclusion / Recommendation

---
# Problems-to-be-addressed:

a. In order automate the categorization process for better sub-topic organization for a big forum like Reddit, how can we distinguish posts that are from similar categories like 'pokemon' and 'pokemontrades' respectively? 

b. What are the major concerns of 'pokemontrade' and 'pokemon'? What are the subtle differences that can distinguish these two from each other?

c. What are the heated topics that are discussed among the users in both 'pokemon' and 'pokemontrade' subreddits?

d. Who are the influencers who have the most subscribers?

e. Are adults the majority of the users in these forums?


## 2. Data Collection

This project will use Pushshift's API to conduct webscrapping to collect all posts from subreddit 'pokemon' and 'pokemontrades'


## 3. Data Cleaning & EDA

For the EDA, a sentiment analysis will be provided to analyse some of the main keywords that contribute to a specific subreddit accordingly, using Word Cloud etc. Afinn score will also used to evalaute the sentiment in each forum.

AFINN is an English word listed developed by Finn Årup Nielsen. 
#Words scores range from minus five (negative) to plus five (positive). 
#The English language dictionary consists of 2,477 coded words.


4. Preprocessing & Modeling

**Option 1: Pipeline: CountVectorizer + MultinomialNB**

**Option 2: Pipeline: CountVectorizer + Term frequency Inverse document frequency (TFIDF) +  MultinomialNB**

## 5. Evaluation and Conceptual Understanding

For predictive modeling, this project aims to compare the accuracy of a pipline that encompass CountVectorizer and MultinomialNB, versus one that encompass CountVectorizer and TfidfVectorizer. What CountVectorizer does is to transform a given text into a vector on the basis of the frequency (count) of each word that occurs in the entire text. This provides a foundation to apply both multinomial Naive Bayes classifier and Term frequency Inverse document frequency (TFIDF) at a later stage.


Multinomial Naive Bayes classifier is a probabilistic learning method that is mostly used in Natural Language Processing (NLP). The algorithm is based on the Bayes theorem and predicts the tag of a text such as a piece of email or newspaper article. It calculates the probability of each tag for a given sample and then gives the tag with the highest probability as output.

Naive Bayes classifier is a collection of many algorithms where all the algorithms share one common principle, and that is each feature being classified is not related to any other feature. The presence or absence of a feature does not affect the presence or absence of the other feature.


While on the other hand, Term frequency Inverse document frequency (TFIDF) is a statistical formula to convert text documents into vectors based on the relevancy of the word. It is based on the bag of the words model to create a matrix containing the information about less relevant and most relevant words in the document. 

TF-IDF is particularly useful in NLP tasks, topic modeling, and machine learning tasks. It helps algorithms to use the importance of the words to predict outcomes. 


In this project, we are going to compare the accuracy from each of these models and find out the best one which can help better predict the topic of the post and the subreddit that they should belong to.

## 6. Conclusion / Recommendation
According to the accruacy score shown below, Term frequency Inverse document frequency (TFIDF) crowns an accuracy score of 95% testing R2 score, which apparently does a slightly better job on classifying the reddit posts by just  MultinomialNB, which has 94% testing R2 score.

The reason why it performs slightly better is because Term frequency Inverse document frequency (TFIDF) convert text documents into vectors based on the relevancy of the word, it takes natural human communication context into account. Comparing to a sole MultinomialNB, which only calculates the probability of each tag for a given sample, it didn't consider any contexts nor associating other features. Probabiltiy is its sole priority, which may or may not resemble entirely what a natural context is like for communicating online. 
