# Tweet Sentiment Analysis
Allison Gao, Meaghan Ross, Raylin Soriano

![image-1](https://cdn.analyticsvidhya.com/wp-content/uploads/2018/07/performing-twitter-sentiment-analysis1.jpg) <br />

# Business Understanding


This analysis used over 9,000 Tweets on Apple and Google products to build an NLP model to analyze consumer sentiment. 
The purpose of the analysis is to provide actionable recommendations for a client seeking to purchase a consumer sentiment tool that is able to detect product sentiment based on Tweets. Clients interested in detecting product sentiment for purposes of market segmentation can use this project’s findings to inform its business decision. 

# Data & Methodology

#### Data Source
The dataset comes from CrowdFlower via data.world. 

https://data.world/crowdflower/brands-and-product-emotions

#### Data Shape
The entire raw dataset contains 9094 rows and 3 columns. Each row represents a Tweet while each column specifies a feature. The columns are content of the tweet, what type of emotion was detected based on the Tweet, and what company the Tweet was directed at. Human raters rated the sentiment in over 9,000 Tweets as positive, negative, no emotion detected, or “I can’t tell”. 

This is a highly imbalanced dataset. Close to 60% of the Tweets were labeled as no emotion, 32% were associated with positive emotion, 6% were associated with negative emotions, and 1.7% were labeled as “I can’t tell”. Given the small percentage of Tweets under unable to detect, we excluded these from our dataset, resulting in a three-class target variable. The three classes are positive emotion, negative emotion, and no emotion detect. 

For our analysis, our target variable is type of emotion detected, which we narrowed down to negative emotion, positive, and no emotion. 

## EDA

This word cloud shows the unique words found from postive tweets from our data.

<img width="476" alt="Screen Shot 2021-10-07 at 3 04 11 PM" src="https://user-images.githubusercontent.com/40476299/136446852-d4569765-5728-434b-be65-81e9863c7975.png">


This word cloud shows the unique words found from negative tweets from our data.

<img width="472" alt="Screen Shot 2021-10-07 at 2 56 40 PM" src="https://user-images.githubusercontent.com/40476299/136446922-4e249163-7bc0-4b2c-91ca-a2acd35eb087.png">
<br>

This graph shows the relationship between the lenght of the postive and negative tweets. Looking at graph it shows that the length of the tweet does not really impact on whether a tweet will be labeled as positive, negative or no emotion based on the length.

<img width="843" alt="Screen Shot 2021-10-07 at 2 57 04 PM" src="https://user-images.githubusercontent.com/40476299/136446447-707d62d8-8382-48b9-a706-cce6f3dad900.png">





# Final Model
We choose the Multinomial Naitve Bayes as our final model. 
It has a Accuracy Score of 66% and a Macro Precision Score of 70%

<img width="509" alt="Screen Shot 2021-10-07 at 2 57 27 PM" src="https://user-images.githubusercontent.com/40476299/136446470-f3e0b9fb-1486-4525-9ccb-5fc601ca5d6e.png">


# Conclusion
We saw that our best model was the Multinomial Naive Bayes with the Tf-IDF Vectorizor at dectecting tweet sentimemt. 

# Next Steps
For next steps we would like to include deep-learning such as Word2Vec to help create more precise models. 

Also including the the tweets from the "I can't tell" is can better prepare prepare for unseen data.

# Project Structure
```
├── README.md
├── Individuals Notebooks       <--- Directory for individual workspaces
│   ├── allison
│   ├── meaghan
│   ├── raylin
│   
├── Presentation.pdf   
├── final.ipynb     
└── .gitignore
```
