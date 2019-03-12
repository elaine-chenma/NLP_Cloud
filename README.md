# NLP\_Cloud


# Sentiment Analysis on Amazon Products
Elaine MA, MSBA, UC Davis
Mar 4th, 2019
## Colab Link
[https://colab.research.google.com/drive/1_ZQT23H1XWVNfrvy_JnVFoCTaYOZ9XXf ][1]
## Objective
In this notebook, I aim to apply sentiment analysis on Amazon product rating data. TextBlob is a widely used package for text analysis with Python. However, in this notebook, I will use two Cloud resources to automate the sentiment analysis process.
- AWS Comprehend
- Google Cloud Natural Language

## Exploratory Data Analysis
16.7% of the whole product ratings only have 1 star, the lowest star that customers can leave. 1 star means customers are very unsatisfied with the product, hence we can assume that their comments are very negative. Let’s test with two cloud sentiment analysis engines!

## Modeling
1. AWS Comprehend API
The comprehend API returns the most likely sentiment for the text as well as the scores for each of the sentiments: positive, negative, mixed, and neutral. The score represents the likelihood that the sentiment was correctly detected. For Amazon 1-star reviews, Comprehend classified 782 out of 836 as negative, and 29 as positive. 
![pic1]()(/images/Picture1.png)

2. Google Cloud Natural Language
Unlike AWS Comprehend, Google Cloud NL Sentiment analysis attempts to determine the overall attitude (positive or negative) expressed within the text. Sentiment is represented by numerical score ranging from -1 to +1 and magnitude values ranging from 0 to 1.  Cloud NL returned 760 out of 836 as negative, and 15 as positive.
![pic2]()(/images/Picture2.png)


## Recommendation for Cloud User
From above analysis, we can see that both AWS Comprehend and GCP NL returns negative-sentiment judgement for most of the reviews that comes with rating 1. Due to the limited number of free APIs calls with these two cloud service, we did not proceed with topic modeling on reviews, which can be easily done with AWS and GCP APIs like what we did with sentiment analysis. Topic modeling can help us further understand why customer has low ratings and hence improve the product.

In terms of the choice between AWS Comprehend and GCP NL, both cloud computing are easy to implement and their returns are easy to interpret. I would prefer GCP NL more at the time being as it returns the magnitude of a document's sentiment, which indicates how much emotional content is present within the document, and this value is often proportional to the length of the document.

[1]:	https://colab.research.google.com/drive/1_ZQT23H1XWVNfrvy_JnVFoCTaYOZ9XXf
