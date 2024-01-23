# Data analysis and supervised learning on Reddit comments and TSLA stock data
Performed data analysis and supervised learning on dataset of one year's worth of Reddit comments mentioning TSLA and one year's worth of TSLA stock data.
Used matplotlib for data visualizations.
Used pandas and scikit-learn for data analysis and prediction.

<p>&nbsp;</p>

**Datasets**

<h4>Reddit dataset:</h4>
URL: https://www.kaggle.com/datasets/pavellexyr/one-year-of-tsla-on-reddit?resource=download

Credit: Lexyr

This dataset contains all posts and comments containing the term "TSLA" submitted to Reddit between July 5th, 2021 to July 4th, 2022.

Relevant fields include:
- subreddit.name: the subreddit where the post/comment was made
- created_utc: the UTC timestamp of the post/comment
- body: (comment only) the text data of the comment
- sentiment: (comment only) the sentiment score for the comment
- score: the score of the post/comment (total 'upvotes' minus total 'downvotes')

<h4>TSLA dataset:</h4>
URL: https://finance.yahoo.com/quote/TSLA/history?p=TSLA

Credit: Yahoo! Finance

This dataset contains the daily historical pricing data for TSLA from July 5th, 2021 to July 4th, 2022.

<p>&nbsp;</p>

**Research questions and results**

- There have been instances where individuals are influenced by social media to purchase shares at inflated prices, which could further drive up the share price. Large gains in value over a short period of time then incites further excitement on social media. Which of these factors is stronger? Does sentiment on Reddit predict changes in share price, or does share price predict sentiment on Reddit?
  
    There is evidence that there is a stronger relationship between changes in share price and reddit sentiment compared to actual share price and reddit sentiment.

- Are some subreddits better at predicting share price than others? Which communities are more 'reactionary' and which are more 'predictive'?
  
    Certain subreddits are more volatile in their opinions of the stock compared to others. /r/stocks, for example, showed less extreme attitudes towards TSLA.

- Is the score of a post/comment an indicator of its reliability? Do higher scoring posts/comments have higher predictive utility compared to lower scoring ones?
  
    This question remains unanswered, as the sentiment of reddit comments in general were not able to improve predictions regarding TSLA.

Graphs:

Low correlation between share price and reddit sentiment.

<img width="429" alt="price_sentiment" src="https://github.com/chanjdaniel/reddit_tsla_data_analysis/assets/97641190/26672a12-3de2-4949-b3da-f66c03f7ea44">

Stronger relationship between comment counts and trading volume.

<img width="430" alt="trad_vol_comm_count" src="https://github.com/chanjdaniel/reddit_tsla_data_analysis/assets/97641190/31e5e0d8-38f5-4c9d-849f-6e4886a83b00">

Feature importances suggest that higher comment counts contribute more to model predictions of higher share price compared to sentiment.
The subreddits "wallstreetbets" and "stocks" have more influence than the rest of reddit.

<img width="536" alt="feat_import" src="https://github.com/chanjdaniel/reddit_tsla_data_analysis/assets/97641190/96e061ff-863e-45d0-ba7f-8af5e743cdff">

<p>&nbsp;</p>

**Limitations and future directions**
1. Low number of data points
   * One year of stock data yields data points from ~250 trading days
   * Need to collect data across a longer time period
2. Low amount of information extracted from comments
   * Instead of only sentiment, need to extract richer features from comment data
   * Get token counts using CountVectorizer
   * Get vectorized semantic content using word2vec
