![](Images/ethereum-and-bitcoin.jpg)
# Sentiment Analysis of Crypto Currencies: Ethereum
### Author: Eric Romano
## Overview

During the week of May 15th , the market experienced a volatile environment for cryptocurrencies with Bitcoins plugging to half of it all time high of $60,000. A total of $830 billion lost by investors causing many investors to go bankrupt.

## Business Problem 

Many retail investors would like to have tools to have at there disposal to make predictions that can lead to better returns or better exit strategies. The crypto market is strongly connected to retail investors and their emotions. Using Sentiment Analysis and other metrics such as Relative Strength Index we believe these will be useful in creating tools that will classify if the market closes higher or lower than the day before. The first crypto currency that will be explored in is Ethereum and will use these models to use for other top trending crypto currencies.
1. Can we successfully use sentiment analysis features to classify if the market will close higher or lower than the previous day?
2. Can we extract features using financial technical analysis tools such as Relative Strength Index that is used when evaluating momentum?  To visualize and isolate conditions of overbought and oversold 
3. Can previous historical data, such as the day before, be a strong feature used in modeling?
4. What are the important features of the models and can we extract promising insight for these features that can be used in creating investment strategies?

### Hyptheses

Null Hypothesis (H0): There is no relationship between the historical data features with sentiment analysis features and close higher or lower classifier. 

Alternative Hypothesis (Ha): There is a relationship between the historical data features with sentiment analysis features and close higher or lower classifier.

## Data Understanding 

CoinMarketCap is the world’s most-referenced price-tracking website for crypto assets. Providing retail users with unbiased, high quality and accurate information. With-in this site you can extract important data and is the main platform used to acquire the data used in this model. All news headlines were scraped from a time frame starting from March to June to possibly extract insights about this highly volatile environment.

This dataset contains 285 rows x 41 columns.

## Method

The analysis performed in my Jupyter Notebook follows a CRISP-DM method approach. Imported data form a reputable source, cleaned, processed, and feature engineered. Using Natural Language Processing techniques and modeling techniques to create a classifier that makes predictions about if the Ethereum market will close higher or lower than the previous day. Using descriptive statistics to determine promising insights and trends within the Ethereum market. Utilizing Random Forest and Linear Discriminant Analysis models to assess the most important features that improve the models. To ensure that the model produces the most promising results recall should be optimized to limit false negatives. 

## Results 

![](Images/Price_RSI.png)

One of the indicators used to create engineered features was the Relative Strength Index which is a metric that can be used to understand if the current market is being overbought or oversold. From the chart above you can see when Ethereum crossed the overbought bar and touched the 90% level right before a large sell off occurred. 

![](Images/Sentiment_Analysis_Compound_vs_Date.png)

In this sentiment analysis of just news headlines there was an overall positive compound value trend leading up to the rise of the all-time highs right before the crash. 

![](Images/fig5.png)

In the model that included features engineered from the sentiment analysis and the relative strength index the most important features were the new center id, bought_sold and low_class. 

![](Images/fig6.png)

Surprisingly, when including the previous day values of the historical data set it provide a strong importance to our final models. The strongest being the volume value of the previous day. 

## Evaluations

In this analysis the goal was to correctly classify if the market will close higher or lower than the day before. The first model consisted of engineered features made from a sentiment analysis of news headlines. The modeling techniques used in this analysis were both Linear Discriminant Analysis(LDA) and a Random Forest(RF). 

![](Images/classification_report_LDA_SA.PNG)

For the first base line LDA model we see that recall is about 90 percent when classifying if the day will close higher than the day before. As for classifying if the day will close lower than the day before, this value was as low as 31 percent.

![](Images/classification_report_RF_SA.PNG)

As for the RF model, the model's classification of lower days increased by about 20 percent but saw a decrease in classification of higher days.

I decided to feature engineer more variables out of historical data. The first was utilizing the Relative Strength Index to create features that help indicate when something is being over bought or oversold. The next features that were created were extracted from historical data. We will be prioritizing recall to limit the number of false negatives. 

False negative will classify a day that will close lower than the day before however the actual result is the day closing higher. In some cases, this might give investors the wrong insight when creating investment strategies or exist strategies. Due to this I believe another metric to gauge the performance of these model is accuracy. 

![](Images/confusion_matrix_LDA_all.png)

![](Images/classification_report_LDA_All.PNG)

![](Images/confusion_matrix_RF_all.png)

![](Images/classification_report_RF_All.PNG)

When including the features from the previous values of the historical data the model either becomes overfitted or the model has the right features to make great predictions. In order to answer this we need to continue to gather more data. 

## Conclusion

In conclusion, the combination of engineered features from the historical data set and the features from a sentiment analysis provide a great foundation to models to predict whether the Ethereum market will close higher or lower than the previous day.  Looking into just the months leading up to these all-time highs and before the crash our models provide actionable recommendation to help investors possibly make more informed investments.

### Recommendations 

1.	Look into the new centers that provide the strongest correlations to the market. Keeping them in your daily reading list will be your best use of time in trying to get information on Ethereum. 
2.	Utilizing the RSI is useful specifically the bought and sold feature as it provides you better prediction power to determining if the market will close higher or lower than the previous day. 
3.  One feature to keep in mind is monitoring the low historical data. This provides you with the lowest the coin is being traded at. 
4.  The strongest feature was the volume value of the previous day. The trading volume is a techincal indicatior that represents the overall activity of a security or market. This can be use to legitmize a it's price action, which can then help investors in their decision to either buy or sell. 

### Future Work 

The model is a great baseline that will be used to explore the top altcoins as well as bitcoin. Also, I will explore if the important feature remains important across all the other cryptocurrency.  I would also like to extend the time to a whole year to gather more data to add into the model. By adding more data points, we will be able to see if the model remains a great model or if there is a significant decrease in the metrics that were used to evaluate the performance of the model. 

## For More Information

Please review my full analysis in my [Jupyter Notebook]() or my [presentation]().
For any questions, please contact Eric Romano at egustavo94@gmail.com 

For any additional questions, please contact **Eric Romano** at [egustavo94@gmail.com](egustavo94@gmail.com).

## Repository Structure

```bash

├── .ipynb_checkpoints                      < Folder containing saved checkpoints
├── Images                                  < Folder containing image files used for this project
├── Tweet_Ethereum                          < Folder containing CSV file for future work
├── Ethereum_close_prediction_model.ipynb   < Narrative documentation of analysis in Jupyter notebook
├── Historical_Data.ipynb               < Narrative documentation of webscrapping in Jupyter notebook
├── README.md                               < The top-level README for reviewers of this project
├── RSI_Over_sold.ipynb                     < PDF version of Jupyter notebook
├── Web_Scrapping_headlines.ipynb       < Narrative documentation of webscrapping in Jupyter notebook
├── Web_Scrapping_Tweets.ipynb          < Narrative documentation of webscrapping in Jupyter notebook
├── df_ethereum_headlines.csv               < CSV file used for this project
├── df_historical_data.csv                  < CSV file used for this project
├── historical_data.csv                     < CSV file used for this project

```
