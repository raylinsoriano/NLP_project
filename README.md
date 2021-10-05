# Tweet Sentiment Analysis
Allison Gao, Meaghan Ross, Raylin Soriano

![image-1](https://cdn.analyticsvidhya.com/wp-content/uploads/2018/07/performing-twitter-sentiment-analysis1.jpg) <br />

# Business Understanding


This analysis used over 9,000 Tweets on Apple and Google products to build an NLP model to analyze consumer sentiment. 
The purpose of the analysis is to provide actionable recommendations for a client seeking to purchase a consumer sentiment tool that is able to detect product sentiment based on Tweets. Our analysis shows XYZ. Clients interested in detecting product sentiment for purposes of market segmentation can use this project’s findings to inform its business decision. 

# Data & Methodology

Data Source
The dataset comes from CrowdFlower via data.world.

Data Shape
The entire raw dataset contains 9094 rows and 3 columns. Each row represents a Tweet while each column specifies a feature. The columns are content of the tweet, what type of emotion was detected based on the Tweet, and what company the Tweet was directed at. Human raters rated the sentiment in over 9,000 Tweets as positive, negative, no emotion detected, or “I can’t tell”. 

This is a highly imbalanced dataset. Close to 60% of the Tweets were labeled as no emotion, 32% were associated with positive emotion, 6% were associated with negative emotions, and 1.7% were labeled as “I can’t tell”. 

Given the small percentage of Tweets under unable to detect, we excluded these from our dataset, resulting in a three class target variable. The three classes are positive emotion, negative emotion, and no emotion detect. 

For our analysis, our target variable is type of emotion, which we narrowed down to negative emotion, positive and no emotion. 

## EDA




# Final Model


# Conclusion


# Next Steps



# For More Information

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
