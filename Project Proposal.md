# Playstation State of Play Community Sentiment (twitter)

## Question
### Framing
Sony's Playstation division has decided they want to better understand the community response to their state of play livestreamed events. They want the sentiment at a topic level, as they generally present 5-10 game trailers and hardware announcements. Their reasoning is that knowing positive and negative reactions can help inform their digital media posting strategy.

### Benefits
By understanding the community reactions/sentiment around the state of play Playstation can:
* prioritize social media campaigns for well received trailers/announcements to continue and develop further the interest in the topic
  * Also knowing which topic received the most tweets is informative for improving future trailers/announcements
* de-prioritize poorly received trailers/announcements to let the online community "cool-off" on the topic before beginning social media campaigns.

## Data
### Source
There are 2 potential sources for this data. The primary source is Twitter. For the state of play that aired 2/25/2021 there were [~12k tweets](https://www.exportdata.io/trends/united-states/2021-02-25/15) (listed as mid to low 30's in this link). The other option, which I don't plan on doing unless the twitter option falls through, is to use the comments on the state of play youtube videos. These videos have 3,000 - 5,000 comments each.

### Individual Sample
One sample is 1 document, which is 1 tweet or comment. Depending on volume, I will likely control for quote tweets and/or replies.

### Features/Characteristics
I will be looking at the tweet contents for the features. 

### Target
There are 2 primary "targets". The first is to model topics for the tweets about state of play. The 2nd is to do a sentiment analysis on the tweets to understand if reactions were positive or negative, preferably at the topic level.

## Tools
### Meeting Tools Requirements
I plan on using sklearn, pandas, NLKT or spaCy (pre-processing and topic modeling), and scattertext potentially for visualization. If I have time I would like to explore flask to make a web-app that could be refreshed for each state of play.

### Main Algorithms/Process Flow
There are 2 main phases. We will learn about topic modelling, but from cursory reading it looks like I will use PCA, SVD, or NMF methods for topic modeling and dimensionality reduction

The 2nd phase is the sentiment analysis. There are a couple of options, but it looks like NLTK, spaCy, and text blob all have some level of sentimental rating for each document that can be incorporated into the sentiment analysis by the modeled topics.


## MVP
Modeled topics for the specific state of play event, as well as a word cloud for each topic.
