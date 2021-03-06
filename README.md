# Tweet Sentiment Analysis
Allison Gao, Meaghan Ross, Raylin Soriano

![image-1](https://cdn.analyticsvidhya.com/wp-content/uploads/2018/07/performing-twitter-sentiment-analysis1.jpg) <br />

## Overview
We built a project using Natural Language Processing (NLP) baseline to analyze consumer sentiment from tweets from the SXSW conference where they were announcing the new iPad2.

## Business Problem
The purpose of the analysis is to provide actionable recommendations for our client Samsung seeking to purchase a consumer sentiment tool that is able to detect product sentiment based on tweets. Clients interested in detecting product sentiment for purposes of market segmentation can use this project’s findings to inform its business decision. 

## Data & Methodology

#### Data Source
The dataset comes from CrowdFlower via data.world found [here](https://data.world/crowdflower/brands-and-product-emotions).
The data was collected from twitter users attending the 2011 South by Southwest conferences and festivals.

#### Data Shape
The entire raw dataset contains 9094 rows and 3 columns. Each row represents a tweet while each column specifies a feature. The three columns are content of the tweet, what type of emotion was detected based on the Tweet, and what company the Tweet was directed at. Human raters rated the sentiment in over 9,000 Tweets as positive, negative, no emotion detected, or “I can’t tell”. 

This is a highly imbalanced dataset. Close to 60% of the tweets were labeled as no emotion, 32% were associated with positive emotion, 6% were associated with negative emotions, and 1.7% were labeled as “I can’t tell”. Given the small percentage of tweets labeled as unable to detect, we excluded these from our dataset, resulting in a three-class target variable. The three classes are positive emotion, negative emotion, and no emotion detect. 

## EDA

Since this dataset's tweets came from the South by Southwest event, several words like #SXSW and iPad appeared in all three emotion groups in the target variable. As a result, we wanted to pull the unique words from the positive and negative emotion groups for exploratory analysis. 

* This word cloud shows the unique words found from positive tweets from our data.

<img src="images/positive_tweets.png"><br>
* This word cloud shows the unique words found from negative tweets from our data.

<img src="images/negative_tweets.png"><br>

* This graph below shows the distribution of the length of both positive and negative tweets. Looking at the graph it shows that the length of the tweet does not impact on whether a tweet will be labeled as positive, negative or no emotion based on its length.

<img src="images/tweet_length.png"><br>
## Modeling
<img src="images/model_iterations.png"><br>

We used accuracy and precision as our two key metrics to evaluate our models. In particular, we focused on increasing the precision score. We want our model to correctly identify true emotions within each class while minimizing the false positives. 
For our baseline model, we used a CountVectorizer and a Multinomial Naive Bayes, which gave us 67% in accuracy and 65% in precision. We then moved to using Tf-Idf Vectorizer with the rest of the four models.  As an effort to increase our key metric’s score, we tried out different tuning options on logistic regression, random forest, and XGBoost. At the end of our iteration process, we could not increase our accuracy and precision scores. 

As shown on the table, logistic regression produced the lowest accuracy and precision score while Multinomial Naive Bayes produced the highest precision score. 

## Final Model
<img src="images/final_model_schema.png"><br>
* Before modeling, the tweets were preprocessed. First, a TweetTokenizer was implemented to split the tweet text into words while keeping hashtags and handles intact. 
* Then the text was lowercased and stop words were removed. 
* In the last step of preprocessing the text was put through a lemmatization process to convert words to their base forms using their part of speech. 
* After performing a train-test split, the tweet text and the target were then loaded into a model pipeline that included a TF-IDF vectorizer, followed by SMOTE to slightly oversample the negative emotion class. 
* Finally, the data and their TF-IDF scores were put through a Multinomial Naive Bayes model to predict the sentiment of the original tweet.

#### Results
The final model has an **Accuracy Score of 66%** and a **Macro Precision Score of 70%**.

<img src="images/final_model_cm.png"><br>


## Conclusion
* Per our business problem, we believe Samsung should implement the Multinomial Bayes model using TF-IDF Vectorizer and SMOTE as it is the best overall model for taking in text from tweets and precisely categorizing the sentiment.  
* Samsung could avoid using costly human coders in the process of sentiment analysis by using this model to correctly predict tweet sentiment.  

## Next Steps
* We would like to include deep-learning such as Word2Vec to help create more precise models. 

* Include the tweets classified as "I can't tell" to better prepare for unseen data.

## For More Information
See the full analysis in the [Jupyter Notebook](Final_Notebook.ipynb) or review [this presentation](Twitter_Sentiment_Analysis.pdf).

Allison Gao:  allison.gao@nyu.edu <br />
Meaghan Ross: mer423@nyu.edu <br />
Raylin Soriano: sorianoraylin@gmail.com <br />

## Project Structure
```
├── Individuals Notebooks       <--- Directory for individual workspaces
│   ├── allison
│   ├── meaghan
│   ├── raylin
│   
├── data
├── images
├── README.md
├── Twitter_Sentiment_Analysis.pdf   
├── Final_Notebook.ipynb     
└── .gitignore
```
