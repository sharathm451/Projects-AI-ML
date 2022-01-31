
# Twitter Sentimetal Analysis

 Twitter is a social platform where most people tweets and express their opinions and facts.

 ### Aim:
  To pick any required query and find out the Sentimetal Analysis of it.

 ### Requirements:
 To start the Project, we need a twitter developer account to scrape the text.
 You want to collect text data using Twitter API 

 After creating the account, also open new App/project in the account which gives secured credentials to access the twitter content.

 There are Two types of credentials:

  - Consumer API keys [API key and API secret key]
  - Access token keys [Access token key, Access token secret key]

Consumer keys are associated keys to the twitter API and secret key is a password to authenticate with the authentication server.

Access token are the keys which is given to the client when successful authentication is done using consumer API keys, and againg secret key is a password to the client authentication 


# 
## Installation


```bash
https://anaconda.org/conda-forge/tweepy

https://anaconda.org/anaconda/openpyxl

```
    
 - tweepy(Twitter python) is a open source library which is actually hosted on github enables the python to communicate with the twitter platform using API and its keys.
 - openpyxl is a python library to read or write excel 2010 documents like xlsx / xlsm / xltx / xltm supported files.
 - OAuthHandler is also from tweepy used to connect local jupyter notebook to the API with the credential keys.


 ### Import packages

  - import the required packages

### credetials

  - Note the required API credentials

### Call API

 - call the API using consumer keys and access tokens and their secret keys of each.


### Lets provide the query

 - choose a query and provide it properly
 - fetch the tweets (you will get it in the json format with dictionary 
 - count = 10 catches top 10 tweets, exclude = retweets (which excludes), tweet mode = extended 
 - There are two types of tweet modes : compatiblity and extended.  By default tweepy sets compatiblity mode, the text attribute of status object is written by tweepy and extracts only truncated 140 characters. 
 - it is advised to use the extended mode to refuse the truncated extraction and access fully.


### Getting the tweets and some of its related attributes

 - when you wanted the tweets, it contains many attributes like tweet date, user, user verified, user status count, fav count, rt count, user location and many more 
 - you can use the required attributes along with tweets.
 - api.search is limited to fetch the only 100 tweets at a time but tweepy.Cursor allows to fetch the tweets as many as of our desired. Here we need 1000 tweets so Cursor fetches 100 tweets and stores in a page and next fetches another 100 tweets and stores in a page as it goes on till the loop breaks.  
 - Use clean tweet function using the regular expressions or other way to clean the tweets from the unnecessary symbols and special characters.
- textblob is module which has a in-built sentimental analysis property.
- Sentiment(polarity, subjectivity)
- Polarity: it is a float score within a range [-1, 1]
- subjectivity: it is a float value within the range  [0, 1] where 0 means Objective(about facts) and 1 means subjective(about opinions)

### Sentimental analysis
 - Using textblob set polarity > 0 for positve 
 - set polarity == 0 for neutral and < 0  for negative.
 - set pd.set_option for maximum tweet width visibility.

### Query sentimental length
 - Get the length or number of positve, neutral and negative tweets.

# Note:
 from the length or number of positve, negative and neutral tweets, we can get to know the people opinions or facts about the query on this basis.


 
 
