# Twitter Scrapper

A project written in Python to get old tweets, it bypass some limitations of Twitter Official API.

## Details

This code is based on this one:

>https://github.com/Jefferson-Henrique/GetOldTweets-python

It has been rewrote to work properly on Python3. There's work still in progress (use of more modern libraries, etc)

Twitter Official API has the bother limitation of time constraints, you can't get older tweets than a week. Some tools provide access to older tweets but in the most of them you have to spend some money before.
This code imitates how Twitter Search through a browser works: when you enter on Twitter a scroll loader starts, if you scroll down to get more and more tweets, all through calls to a JSON provider.

## Prerequisites

The code has been modified to be used with Python3 and I has not been tested in Python2.

Expected package dependencies are listed in the "requirements.txt" file for PIP, you need to run the following command to get dependencies:

'''
pip install -r requirements.txt
'''

## Components
- **Tweet:** Gives some information about a specific tweet.
  - id (str)
  - permalink (str)
  - username (str)
  - text (str)
  - date (date)
  - retweets (int)
  - favorites (int)
  - mentions (str)
  - hashtags (str)
  - geo (str)

- **TweetManager:** (WIP)A manager class to help getting tweets in **Tweet**'s model.
  - getTweets (**TwitterCriteria**): Return the list of tweets retrieved by using an instance of **TwitterCriteria**.

- **search_tweets:** Export tweets to a json file.


## Examples of command-line usage
- Get help use
```
    python Exporter.py -h
```
- Get tweets by username
```
    python Exporter.py --username "barackobama" --maxtweets 1
```    
- Get tweets by query search
```
    python Exporter.py --query "europe refugees" --maxtweets 1
```    
- Get tweets by username and bound dates
```
    python Exporter.py --username "barackobama" --since 2015-09-10 --until 2015-09-12 --maxtweets 1
```
- Get the last 10 top tweets by username
```
    python Exporter.py --username "barackobama" --maxtweets 10 --toptweets
```
