# Data-Wrangling
data wrangling on a we-rate-dogs dataset from twitter

# introduction

WeRateDogs is a twitter account rate the dog stages and has millions of users
I wrangled the data in the wrangle_act.ipynb, and the wrangling process included the following steps:

# 1-data gathering

- I downloaded the data set twitter_archive_enhanced.csv provided in the workspace
- then gathering the tweets data set using twitter API tweepy
- then gathering the image_predictions.tsv provided in the workspace

# 2-data assessing

### -quality

Twitter enhanced archive data set twEnArch twitter_archive_enhanced

- there is decimal rating and the numerator column is int instead of float
- wrong rating numerators were extracted from the text column
- there is no need of column denominator (we add scale to numerator column header )
- null values in retweets columns
- source column need to reformating
- timestamp data type to date
- in_replay_to status id and user id columns need to be converted to appropriate data type
- breeds of the dog are inaccurate
- name columns have null values and misleading values like `a`

### -tidiness

- there are three data sets instead of one master data set
- dog type can be represented in one column instead of three

### note :

there are more quality issues but I choose just 8

# 3-cleaning data

- there is decimal rating and the numerator column is int instead of float 
__i converted the data type to float__
- wrong rating numerators were extracted from the text column
__I reproduced the rating from the text using regex then__
- there is no need of column denominator (we add scale to numerator column header ) 
__I added teh scale to the numerator column header then removed the rating_denominator column__
- null values in retweets columns
__I deleted the rows which have the retweets columns != None so that i will analysis the orgin tweets__
- source column need to reformating
__I extracted the information from the source column and replace it__
- timestamp data type to date
__I converted the timestamp to date data type__
- in_replay_to status id and user id columns need to be converted to appropriate data type 
__I converted these column to string after conveting its content from exp format to int format__
- breeds of the dog is inaccurate 
__i removed the rows which have inaccurate breeds types__
- name columns have null values and misleading values like ’a’
__I re_extract the name of the dog from the text usin regex then replace it__

- there are three data sets instead of one master data set
__I used merge function to make the master data set df by joining the three data sets twEnArch, predictions, tweets__

- dog type can be represented in one column dog_stages instead of four doggo floofer pupper Puppo
__I used merge function to calculate the dog stages column from the four columns__


# Shots 

https://github.com/mostafaGwely/Data-Wrangling/blob/master/act_report.pdf


