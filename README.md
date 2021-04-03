# Capstone Project

### Abstract 				
Using Twitter data, this capstone project takes public opinion as a proxy for community's attitude towards immigrants, and by consequence the predicted success of their integration. The goal is to produce a tool that can be used to visualize the differences in public opinion towards immigrants in different districts in England (through a geographical map). Ultimately, it could be beneficial to further relate community’s attitude to migrant integration and other related facts/events (e.g. reported racial discrimination in the area, job security, education level of immigrants etc...), and raise public awareness of the importance of creating a welcoming environment. 	

**Keywords**: Sentiment analysis, Twitter data, public opinion, immigration, narrative, social integration, England. 

### Data 

The data used in this project consists of tweets posted by users on Twitter, which is retrieved using the Twitter API. A typical query would include the following components.
1. Keyword (Here, the keywords used were: immigration, immigrants, migrants, migration, “border control”, emigration, naturalize, naturalization, citizenship, non-citizenship, borders)
2. Location (defined by the geolocalisation points surrounding each district - forms a polygon)
3. Time window (Here, chosen tweets during the years 2016 and 2020 as they correspond to key Brexit events that would likely suscitate public conversations around immigrants).


Based on the three parameters above, the data is extracted using Twitter’s “full-archive search” endpoint. The amount of data extracted for each district was set to a limit of 2000 tweets per district, for each of the 326 district. However, the number of tweets over that time period and matching the keywords used depend largely on the district and its Twitter traffic. Districts with low twitter traffic matching the keywords used will likely have little or no tweets extracted.

The tweets are then processed to translate the text to English (if it is not already), remove retweet (“RT”) mentions, as well as mentions of the user who retweeted, URLs and line breaks.

### Analysis

Amazon's AWS Comprehend service is used to extract the sentiment from the tweets. 

Each tweet is given the following.
* A “Sentiment” (one of 3 categories: Neutral, Positive, or Negative)
* A “Mixed” score (quantifies how “mixed” the tweet’s sentiment is, on a 0-1 scale)
* A “Positive” score (quantifies the positivity of the tweet, on a 0-1 scale)
* A “Neutral” score (quantifies the neutrality of the tweet, on a 0-1 scale)
* A “Negative” score (quantifies the negativity of the tweet, on a 0-1 scale)


### Visualization 

For each year (2016 and 2020), a map is created, showing how negative and how positive each district is. 
The results are as follows. 

Negativity in 2016: 

![Screenshot] (./Maps/map_negative_2016.png)

Negativity in 2020: 


Positivity in 2016: 

Positivity in 2020: 
