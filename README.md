# Data Wrangling Report
## A Brief Introduction

WeRateDog is a Twitter account that rates people's dogs and allows people to share fascinating comments about them. They have over 4 million followers and have an enormous collection of data in their Twitter archive. **This project aims to demonstrate my wrangling skills** by gathering these data using several methods, Assessing these data, cleaning and storing, and generating insights from the cleaned data.

I have separated the entire process into three different Jupiter notebooks to allow me to deal with the challenges one step at a time. 
The Data-gathering-stage of the project is in the notebook, wrangle_act_1(Data Gathering)

The assessing-and-cleaning-stage is in the notebook, wrangle_act_2(Assessing and Cleaning)

The analysis-and-visualization section is in the notebook, wrangle_act_3(Analysis and visualization).

## Data Gathering
The data gathering stage involved three steps:

- I **Manually downloaded the Twitter archive**  of the WeRateDog Twitter page directly from the link provided on the project page.
- **Programmatically downloaded the image prediction file** using the request library.
- I also queried the Twitter API for additional data, following the steps below:
    - **I created my developer account** 
    requested elevated access through the Twitter review process and was granted access. **I got my api_key and api_key_secret** and went further to generate my access token and access_token_secret. with these keys, I accessed the Twitter API using the tweepy library authentication handler.
    - Using the tweet_id and the tweepy library get_status function, I was able to request the required tweet information, and I saved it line-by-line to a text file. I also read the JSON details into the Dataframe and saved them as CSV.
    - While making the request, some tweet_id returned error '404 not found'. These were caught in a try-except block, and subsequently read into a Dataframe and saved as a CSV file, deleted_tweet.csv.

## Assessing
In the Data assessing stage several tidyness and Quality issues were spotted and properly documented for cleaning. They can be divided into 

The **tydiness** issues and **Quality** issues.

## Cleaning
in the cleaning stage all of the tydiness and cleaniness issues were attended to using several techniques and functions and following the define, code and test framework.

A master dataset containing the cleaned data was generated at the end of the cleaning stage. then this was further divided into the two observational units, tweet_data and image_data.

## Analysis and visualization
In the analysis section of the project, I have developed several insights ranging from patterns observed across the entire data set to specific details obtained as we focus on particular aspects of the dataset. All was  a bid to answer the question, "What are the characteristics of tweet status that attract the most response in terms of retweets and likes."

To answer this question, I went further to pose some more questions like:

What is the relationship between favorite_count and retweet_count?
what is the most liked/retweeted tweet?
How does time affect the value of retweet_count and favorite count?
The most common breed of dog
The most liked breed of Dog
The most popular dog growth stage
sentiment Analysis on the Text is to know how the Tone of the Text influence response.
Best in Class by retweet_count for different dog_growth_stage and for different dog breeds.
At the end of this analysis, several insights were generated and summarized in the conclusion section.