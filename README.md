# NLP Analysis of Tweets About #E32021

## TOC
1. [Tweet API Access Code](https://github.com/phillrich13/NLP-Unsupervised-Learning/blob/main/Tweet%20Gathering.ipynb)
2. [Tweet JSON Consumption Code](https://github.com/phillrich13/NLP-Unsupervised-Learning/blob/main/Tweet%20to%20DF.ipynb)
3. [Topic Modeling and Sentiment Analysis](https://github.com/phillrich13/NLP-Unsupervised-Learning/blob/main/Topic%20Modeling.ipynb)
4. [Visualization and Prep Code](https://github.com/phillrich13/NLP-Unsupervised-Learning/blob/main/Visualizations.ipynb)
5. [Tableau Dashboard](https://public.tableau.com/views/E3TweetSentiments/TopicModelingSentiments?:language=en-US&:display_count=n&:origin=viz_share_link)


## Abstract
The goal for this project was to understand community reactions to the E3 gaming conference via NLP and baseline sentiment analysis. I pulled all tweets over the E3 timeframe with the hashtag #E32021, and removed retweets (since the interest was in reactions, retweets of tweets didn't provide new information). This gave me a corpus of ~120,000 tweets to work with. I then used a TF-IDF vectorizer and NMF Topic modeling to generate a list of 7 topics for tweets about E3. These topics revolved around the biggest presentations at E3, and I then used VADER sentiment analysis to understand community reactions to these topics.

## Design
The design for this project was to understand what the primary topics within tweets about E3. The goal was to develop competitive intelligence around what was viewed positively and negatively on social media from a topic and from specific games. I was also interested in what topics drew the largest amount of social media discussions, and if there were underlying threads that drove the discussion. The applications and take aways can inform social media presence, as well as help inform Playstation's own conferences and what topics/sub topics are popular.

## Data
I used the tweepy package and a twitter developer account to pull from the API all tweets with the E32021 hashtag. This gave me ~380,000 tweets including retweets about E3 saved in JSON files (to protect for any network issues). I then imported the JSON files and removed all retweets because I wanted to only have direct reactions to E3. This lowered the tweet count to ~120,000. I then went through an iterative pre-processing phase to clean the tweets by removing stop words, punctuation, as many emojis as possible, ascii, etc.

## Algorithms
The main unsupervised learning models used were specifically for topic modeling. I used a combination of the following to ensure the best topic generation:

* Count Vectorizer
* TF-IDF Vectorizer
* LSA Topic Modeling
* NMF Topic Modeling

I also tuned the min doc frequency, max doc frequency, and number of topics. Through testing and tuning I found that the best combination was using a TF-IDF vectorizer, NMF topic modeling, and splitting the tweets into sentences (to isolate independent thoughts). This generated the following 7 topics:

* [General E3 tweets](https://user-images.githubusercontent.com/75561764/123307521-6e637100-d4d7-11eb-9778-eba48ac2a188.png)
* [Capcom tweets](https://user-images.githubusercontent.com/75561764/123307617-8f2bc680-d4d7-11eb-8ef3-9f0035bf9dad.png)
* [Ubisoft tweets](https://user-images.githubusercontent.com/75561764/123307675-a2d72d00-d4d7-11eb-92c3-08a2b941cdee.png)
* [Xbox tweets](https://user-images.githubusercontent.com/75561764/123307702-aa96d180-d4d7-11eb-9dec-9c6a4cce7bf5.png)
* [Nintendo (pre-conference)](https://user-images.githubusercontent.com/75561764/123307785-be423800-d4d7-11eb-9b23-43ed83a672f5.png)
* [Nintendo (post-conference)](https://user-images.githubusercontent.com/75561764/123307831-cc905400-d4d7-11eb-917e-7dc2ee297f41.png)
* [Square Enix](https://user-images.githubusercontent.com/75561764/123307880-dc0f9d00-d4d7-11eb-8c95-d7ed6db46b3d.png)


I then used VADER sentiment analysis (tweaking scores of some words in the lexicon to account for game names) to decipher sentiment of tweets about the topics, as well as games presented under the topics.

## Tools
* Python
  * Tweepy - Pull E3 tweets from tweepy api
  * Standard DS libraries (Pandas, numpy, matplotlib)
  * WordCloud package - visualizations
  * SKLearn - vectorization, topic modeling, and sentiment analysis
  
* Tableau - Creating interactive dashboard

## Communication
The primary method of communication is through slides and a [tableau dashboard](https://public.tableau.com/views/E3TweetSentiments/TopicModelingSentiments?:language=en-US&:display_count=n&:origin=viz_share_link)

