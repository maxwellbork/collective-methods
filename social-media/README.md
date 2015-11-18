#Data Mining Social Media Tutorial

##Overview
Description coming soon...

##Getting Started With Tweepy

Tweepy(http://www.tweepy.org) is a Python library for accessing the [Twitter API](https://dev.twitter.com), facilitating access to Twitter data including information about users, tweets, trends, and relationships.

###Tweepy Installation
To install Tweepy using Python 3.x we can use pip, the Python package manager, by issuing the following command in the Terminal:

<pre>
python3 -m pip install tweepy
</pre>

###Twitter API Access
In order to access the Twitter API you need to create a new app using the [Twitter Application Manager](https://apps.twitter.com). 

Once you have registered your app, you need the following pieces of information, available from the 'Keys and Access Tokens' tab of the app, the 'Consumer Key (API Key)' and 'Consumer Secret (API Secret)' found under 'Application Settings,' and the 'Access Token' and 'Access Token Secret' found under 'Your Access Token.' These long strings or random letters and numbers are like keys to the Twitter API. You will need to enter these keys into your Python code. However, do not make them publically available. Remember to remove your keys before commiting your code.

Now you can try some of the Tweepy examples below.

##Tweepy Examples

###Example 1: Post a Tweet
Uses Tweepy to post a tweet to your Twitter account.

<pre>
import tweepy

#Enter the details for your app below.
consumer_key = ''
consumer_secret = ''
access_token = ''
access_token_secret = ''

auth = tweepy.OAuthHandler(consumer_key, consumer_secret)
auth.set_access_token(access_token, access_token_secret)
api = tweepy.API(auth)

status = api.update_status(status='Tweepy is awesome!')
print(status)
</pre>

###Example 2: Get Tweets About Monkeys
Uses Tweepy to return recent tweets about monkeys and outputs details about the tweet including the name, username, date, content, hashtags, etc.

<pre>
import tweepy

#Enter the details for your app below.
consumer_key = ''
consumer_secret = ''
access_token = ''
access_token_secret = ''

auth = tweepy.OAuthHandler(consumer_key, consumer_secret)
auth.set_access_token(access_token, access_token_secret)
api = tweepy.API(auth)

#Enter the term for your search.
searchTerm = 'monkeys'

for tweet in tweepy.Cursor(api.search, q=(search_term)).items(10):
	print('Name:', tweet.author.name)
	print('Screen name:', tweet.author.screen_name)
	print('Date tweeted:', tweet.created_at)
	print('Tweet content:', tweet.text)
	print('Hashtags:', tweet.entities.get('hashtags'))
	print('Retweeted:', tweet.retweeted)
	print('Favorited:', tweet.favorited)
	print('Location:', tweet.user.location)
	print('Time zone:', tweet.user.time_zone)
	print('Location:', tweet.geo)
	print('-----')
</pre>

###Example 3: Get Tweets for a Given User
Uses Tweepy to return recent tweets by a given user, in this case base2john.

<pre>
import tweepy

#Enter the details for your app below.
consumer_key = ''
consumer_secret = ''
access_token = ''
access_token_secret = ''

auth = tweepy.OAuthHandler(consumer_key, consumer_secret)
auth.set_access_token(access_token, access_token_secret)
api = tweepy.API(auth)

#Enter the username of the user who's timeline you want to retreive
username = 'base2john'

tweets = api.user_timeline(username)
for tweet in tweets:
    print(tweet.text)
</pre>

###Example 4: Get Trends for a Location
Uses Tweepy to return recent trends for a given location, in this case New York City.

<pre>
import tweepy

#Enter the details for your app below.
consumer_key = ''
consumer_secret = ''
access_token = ''
access_token_secret = ''

auth = tweepy.OAuthHandler(consumer_key, consumer_secret)
auth.set_access_token(access_token, access_token_secret)
api = tweepy.API(auth)

#Enter a woeid. A woeid is a Where On Earth Identifier that identifies any feature on Earth. This is the woeid for New York City.
woeid = 2459115

trends = api.trends_place(woeid)
print(trends[0]['trends'])
for trend in trends[0]['trends']:
	print(trend['name'])
</pre>

##Getting Started With Facebook Platform Python SDK

Facebook Platform Python SDK is a Python library for accessing the [Facebook Graph API](https://developers.facebook.com/docs/graph-api), facilitating access to Facebook data including information about users, posts, pages, and relationships.

###Facebook Platform Python SDK Installation
Unforutnately, the current release version of Facebook Platform Python SDK is not compatible with Python 3, so we can't use the Python package manager, pip, to install the package. Instead, we need to install the latest version from the GitHub repository. To do this, first download the zip file from here(https://github.com/pythonforfacebook/facebook-sdk/archive/master.zip) and extract it. Assuming the file was downloaded and extracted into your downloads folder, issue the following command in the Terminal:

<pre>
python3 ~/Downloads/facebook-sdk-master/setup.py
</pre>

To use the Facebook Graph API you need an access token. To get an access token, click on the 'Get Token' menu on the [Graph API Explorer page](https://developers.facebook.com/tools/explorer/) and select 'Get User Access Token.' On the following dialog, click the 'Get Access Token' button, and when prompted login to Facebook. The access token is a long string of random letters and numbers that acts like a key to the Facebook Graph API. You will need to enter this key into your Python code. However, do not make it publically available. Remember to remove your key before commiting your code.

Now you can try some of the Facebook Platform Python SDK examples below.

![alt meme]()

##Facebook Platform Python SDK Examples

###Example 5: Facebook Platform Python SDK Example
Description goes here.

<pre>
</pre>

###Example 6: Facebook Platform Python SDK Example
Description goes here.

<pre>
</pre>

###Example 7: Facebook Platform Python SDK Example
Description goes here.

<pre>
</pre>

###Example 8: Facebook Platform Python SDK Example
Description goes here.

<pre>
</pre>

##Resources

* Tweepy Documentation: [http://tweepy.readthedocs.org](http://tweepy.readthedocs.org)
* Facebook SDK for Python Documentation: [https://facebook-sdk.readthedocs.org/en/latest/install.html](https://facebook-sdk.readthedocs.org/en/latest/install.html)