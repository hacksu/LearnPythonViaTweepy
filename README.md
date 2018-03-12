# Learn Python Via Tweepy

If you're here just for the authorization code, skip down to **Authorizing Our Twitter App**

Today we're going to learn the basics of Python, via [Python Anywhere](http://pythonanywhere.com).  Python is language that doesn't come on all computers, so Python Anywhere lets us use it without the pain of installing it manually. 

*If you're interested in installing Python on your local machine, you can do so [here](https://www.python.org/downloads/). it's worth noting that Mac OS has Python 2.7 preinstalled on their machines, but we'll be using Python 3.6. *

## Setting Up Our Project

First, we need to set up an account on [Python Anywhere](http://pythonanywhere.com). You don't even need to confirm your email.

Once you have an account, go to the Files tab, and make a new file called `myScriptName.py` (you can replace `myScriptName` with whatever, just make sure it ends in `.py`). 

With the file open, let's walk through a basic example of a Python script.

Here's a script that will iterate through 15 numbers, and output the square for all of those numbers, with a special message for number 10:

```
for a in range(15):
    b = a * a
    if a == 10:
        print ("You should already know that 10 squared is 100, dummy!")
    else:
        print ("%d squared is equal to %d!" % (a, b))
```

Just hit RUN to check it out!

# Authorizing our Twitter App

***IMPORTANT:*** **Twitter doesn't like spammy twitter profiles, and I don't want to get this account suspended!** I'm giving you authorization to post on the account, and ***every time you run api.update_status successfully,*** it will send out a tweet.  I'm asking that you please limit your posts to ***2 tweets per 10 minutes.*** The twitter limit is 100 tweets/hour, and I don't want us to get banned!

Here's the twitter account this code is hooked up to: [@mic_drop_bot](https://twitter.com/Mic_Drop_Bot)

Once you've read that, you may run the following code to tweet something:

```
# This line imports the library Tweepy, which is pre-installed in PythonAnywhere
import tweepy

# I generated these keys at http://apps.twitter.com
# Note that you need a twitter account with a validated phone number for this
# Please don't abuse this info! 
#
consumer_key = 'msLJGoIZx7hMxWv6eszGGOBfi'
consumer_secret = 'azXQeRpFj9Wowfnrhj1M4CcMgVm5Kp9SXhppPNx26MfLHHivUA'
access_token = '3914186835-ml58nTscOP4TbwuDK1U2aA0YiA1PtlOjlUMPrJH'
access_token_secret = 'JqJdbB4Hj9U52iiEQ1yxDpn2xPxMs0wlx8i3ncCna75LE'

auth = tweepy.OAuthHandler(consumer_key, consumer_secret)
auth.set_access_token(access_token, access_token_secret)
api = tweepy.API(auth)


# Below are some examples of what we can now do -- just uncomment the relevant lines to run

tweet = """
My First Automated Tweet -- hello world!
"""
# Uncomment the next line to send the above tweet:

# api.update_status(status=tweet)

# Uncomment the next line to follow the twitter user @username:

# api.create_friendship('username')

# Uncomment the next 3 lines to print the last 20ish tweets from @_hacksu:

# tweets = api.user_timeline('_hacksu')
# for i in tweets:
#     print (i.text)
```

