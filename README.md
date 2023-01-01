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
5. Evaluation and Conceptual Understanding
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

### A) To better automate the categorization process for better sub-topic organization for a big forum like Reddit, we can we distinguish posts that have the following buzzwords:
## <font color='red'> For 'pokemon' subreddit:</font>
### <font color='red'>Keywords are more likely to be generic. Usually it involves some 'conversational starters', 'greetings' as well as some 'personal opinions' on their favorite pokemons or generations. </font>

<font color='red'>'Happy New year', 'hello', 'hey guys', 'friend', 'pokemon', 'game', 'day', 'favorite', 'gen', 'thought', 'wonder trade'</font>

## <font color='green'>For'pokemontrades' subreddit:</font>
### <font color='green'>Keywords tend to be more specific. Usually, it has to deal with the pokemon's type/personaility/special ability and particular move sets, and whether they are shiny pokemons or not:</font>

<font color='green'>'egg', 'move', 'shiny','adament', 'adament', 'timid', 'levitate', 'mirror coat', 'events', 'trading', 'dream ball', 'beast ball', 'looking, 'offers', 'If', 'evolve', '6iv', 'egg moves'</font>
<font color='green'>'LF' (Looking For),  'FT' (For Trade) (The most crucial differentiators)
  
  ### B) The major concerns of 'pokemontrade' and 'pokemon' resulted in subtle differences:
Pokemontrade subreddit users usually care about about their own mastery of the pokedex, or own pursuits of shiny collections, which tends to be more practical. While for pokemon subreddit users are looking for extending their game network by casual greeting; exchanging friend codes; opinions about different generations and; new game features such as 'Wonder Trade'. 

According to the sentiment analysis, while both subreddits resulted in net positive sentiment scores, pokemontrade tends to indicate higher satisfactory rate and positive emotions. Whereas 'pokemon' subreddit serves as a more generic discussion forum for users to express their opinions. Sometimes, the opinion could be good or bad, depending on the users' experiences. For example, the recent Scarlett/ Violet series was critcised negatively by some for its awful technical aspects, where  the game visual elements were often misplaced and dislocated. On the contrary, 'pokemontrade' seems like more a vibrant, energetic, wishful place where users can throw their wishes out and have them fulfilled accordingly. 
  
  ### C) The heated topics that are discussed among the users in both 'pokemon' and 'pokemontrade' subreddits

 For 'pokemon' subreddit, the most heated discussion topics are probably violet and scarlett, for example, some legendary/special pokemons that are only exclusive to the generation, as well as some general Q&A, opinion seeking related to the game.
 
 For 'pokemontrade' subreddit, the most heated discussion topics seem to be shiny, rare high IV, personality traits / ability pokemons, which people are seeking most of the time.
  
  ### D) The influencers who have the most subscribers

For pokemon market campaigners, they might want to contact the following users to promote their pokemon franchise, as they might have the highest commitment and engagement with subreddit with high quality content:

**'pokemontrade' subreddit:**
</br>
Top users with highest subscribers:


</br>
-Shiny_Star-            11807228.0
</br>
Porygon-Bot             10919769.0
</br>
Theduskwolf              8195275.0
</br>
chenj25                  7680800.0
</br>
hoozayisdead             4543350.0
</br>
MrNoobyy                 4288371.0
</br>
ShaikhAndBake            4091363.0
</br>
enlightened_pogo         3900208.0
</br>
Joedemigod4              3739681.0
</br>
Stanley232323            3678110.0
</br>
FALLGUYS627              3432610.0
</br>
Vanhuie                  3220982.0
</br>
TheGoat1210              3215538.0
</br>
firebird5225             2874154.0
</br>
MrShinobi96              2689109.0
</br>
Beneficial-Gear-7626     2686867.0
</br>
Mikozeki                 2685718.0
</br>
Meowriisa                2685205.0
</br>
rtgreen                  2683799.0
</br>
bwo0                     2618802.0


</br>
**For 'pokemon' subreddit:**
</br>
Top users with highest subscribers:

</br>
EmiKoizuwumi            46068387.0
</br>
cshin09                 37484929.0
</br>
Blueeyeswhiteraichu     24890233.0
</br>
Poll_God                18683148.0
</br>
Bluecomments            16586987.0
</br>
PokeUpdateBot           16278226.0
</br>
AnonymousAzrael         16221707.0
</br>
LightBuzzyear69         15946605.0
</br>
ChrisPChicken04         15046609.0
</br>
EveningChocolate1028    14817777.0
</br>
SnowPhoenix9999         12800880.0
</br>
Under_Master_85         12598236.0
</br>
arthurcdemari           12597202.0
</br>
ChattyBird4Eva          12322406.0
</br>
blaahguy                12296105.0
</br>
wuzhere-75              12272536.0
</br>
Money-Lie7814           12246180.0
</br>
Key_Structure_2070      12242807.0
</br>
NoEnd9111               12056990.0
</br>
Nyuu222                 11885675.0

### E) Whether adults are the majority of the users in these forums

It turns out the kids or people under 18 are the majority accounted for these two subreddit users.

While only a small minority of adults (>10) were engaging in the 'pokemon' subreddit, more adults are engaging with the 'pokemontrade' subreddit instead. This reflects adults focus more on the practicality and unlocking achievements of the game, while kids spend more time in exchanging thoughts and extending network. 

### F) Subreddit Engagement by Word Count
According to the post count, 'pokemontrade' subreddit has significant a larger number of word count compared to 'pokemon'. It is almost double of what 'pokemon' subreddit has, implicating a higher user engagement rate overall. 
