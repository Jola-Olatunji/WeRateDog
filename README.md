A Brief Introduction
We rate dog is a twitter account that rates people's dog and allow people share interesting comments about them. They have over 4 million following and have a large collection of data in their twitter archive. The aim of this project is to demonstrate my wrangling skills by gathering these data  using several methods, Assessing these data, cleaning and storing and generating insights from the cleaned data.

I have separated the entire process into three different jupyter notebook to allow me deal with the challenges one step at a time. 

The data gathering stage of the project can be found in the notebook wrangle_act_1(Data Gathering)

The assessing and cleaning stage has also been stored in the notebook wrangle_act_2(Assessing and Cleaning)

The analysis and visualization can also be found in the notebook wrangle_act_3(Analysis and visualization).

Data Gathering
The data gathering stage involved three steps

I Manually downloaded the twitter archive of the we rate dog twitter page directly from the link provided in the project page.
Programatically, downloaded the image prediction file using the request library.
I also queried the twitter api for addition data following the steps below.
I created my developer account
requested for elevated access through the twitter review process and was granted access. I got my api_key and api_key_secret, went further to generate my access token and access_token_secret. with these keys, I was able to access the twitter api using the tweepy library authentication handler.
Using the tweet_id and the tweepy library get_status function, i was able to request for the required tweet information which i saved line by line to a text file. and i also read the json details into dataframe and saved as csv.
During the process of making the request some tweet_id returned error '404 not found'. These were caught in a try except block and appropriately read into a dataframe and saved as a csv file, deleted_tweet.csv.
Assessing
In the Data assessing stage several tidyness and Quality issues were spotted and properly documented for cleaning.

The tydiness issues are listed below

tidyness issues
The entities field contains more than one data points per observation.
The four fields doggo, floofer, pupper, puppo are all variables of a single field growth_stage
There are six fields in the image_prediction table answering the same question of, what breed is the dog p1, p1_conf, p2, p2_conf, p3, p3_conf.
There are 3 fields in the image_prediction table answering the same question, is it a Dog? p1_dog,p2_dog and p3_dog.
Generally, there are a number of duplicate fields across the table.
There are two observational units in these dataset. The dog details and the tweets details.
The quality issues that were observed were listed below

Quality
Quality issues from the df_twitter_response table

All 23 non null values in in_reponse_to_status_id and in in_reponse_to_screen_name are from the same user, '4196983835', dog_rates.
The user column contains information of the twitter handle We Rate Dogs and its constant for all observation therefore not relevant for the analysis`
favorited, retweeted and is_quote_status have only False values. Since their values are the same for all observations. they are not relevant for our analysis
The following tables have only null values geo,coordinates,place,and contributors.
Quality issues from the df_twitter_archive table

Quality
in_reply_to_status_id field does not contain accurate status id information
in_reply_to_user_id field does not contain significant information for this analysis
retweeted_status_id, retweeted_status_user_id and retweeted_status_timestamp are indication of retweeted status which constitutes duplicated observations.
The required information from the source field is not explicitly expressed in the field
rating_numerator values greater than 15 are most likely not correct.there are 25 observations with values greater than 15
rating_denominator should be 10. There are 23 observations with values not equal to 10
Timestamp column is a string type object instead of a datetime object
Observed some unlikely names in the name column
Quality issues from the df_image_prediction table

Quality
Not all observatons are dogs
Cleaning
in the cleaning stage all of the above tydiness and cleaniness issues were attended to using several techniques and functions and following the define, code and test framework.

A master dataset containing the cleaned data was generated at the end of the cleaning stage. then this was further divided into the two observational units, tweet_data and image_data.

Analysis and visualization
In the analysis section of the project, ii have developed several insights ranging from patterns that can be observed across the entire data set to particular information that can be obtained as we focus on particular aspect of the dataset. all was done in abid to answer the question,"What are the characteristics of tweet status that attracts the most response in terms of retweets and likes."

To answer this question, i went further to pose some more questions like:

What is relationship between favorite_count and retweet_count.
what is the most liked/retweeted tweet.
How does time affect the value of retweet_count and favorite count.
The most common breed of dog
The most liked breed of Dog
The most popular dog growth stage
sentiment Analysis on the Text, to know how the Tone of the Text influence response.
Best in Class by retweet_count for different dog_growth_stage and for different dog breeds.
At the end of these analysis several insights were generated and summarized in the conclusion section.