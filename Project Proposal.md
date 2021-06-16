# E32021 Conference - Community Sentiment (twitter)

## Question
### Framing
A gaming company has decided they want to perform some competitive intelligence on other companies presenting at E3 (6/12 - 6/15). Specifically they want to know what viewers are most interested in, and if possible to know if that interest is positve or negative.

### Benefits
By understanding the community reactions/sentiment around E3 the company can:
* Better plan release date to not coincide with big ticket items
* Review successful presentations & trailers to find common themes to better inform their future trailers
* Understand what is currently driving community interest to potentially improve games in the pipeline

## Data
### Source
I will be scraping as many tweets with the official E3 hashtag over the past week as possible. This should be well over 10,000 tweets.

### Individual Sample
One sample is 1 document, which is 1 tweet or comment. Depending on volume, I will likely control for quote tweets and/or replies.

### Features/Characteristics
I will be looking at the tweet contents for the features. 

### Target
There are 2 primary "targets". The first is to model topics for the tweets about E3. The 2nd is to do a sentiment analysis on the tweets to understand if reactions were positive or negative, preferably at the topic level.

## Tools
### Meeting Tools Requirements
I plan on using sklearn, pandas, NLKT or spaCy (pre-processing and topic modeling), and scattertext potentially for visualization. If I have time I would like to explore flask to make a web-app that could be refreshed for other gaming conferences.

### Main Algorithms/Process Flow
There are 2 main phases. We will learn about topic modelling, but from cursory reading it looks like I will use PCA, SVD, or NMF methods for topic modeling and dimensionality reduction

The 2nd phase is the sentiment analysis. There are a couple of options, but it looks like NLTK, spaCy, and text blob all have some level of sentimental rating for each document that can be incorporated into the sentiment analysis by the modeled topics.


## MVP
Modeled topics for the  E3 event, as well as a word cloud for each topic.
