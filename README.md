# AlgoTrading_NLP_based_portfolios
This is a project scheme aiming at constructing a portfolio using machine learning approaches for making dynamic investment decision. Serval perspectives and dimension are used as predictors based on both financial, economic and statistical concept to build a comprehensive model. These includes but not limited to market data and technical indicators, company's financial fundamentals, regional economic status and its expectation, and effect on financial news. 

A series of mini projects are performed for testing some hypothesis and thought. Important finding will be released and updated regularly. 


# Directory:
1. Basic Natural Language Processing on News Title to classify Stock Trend (you are here!)


## 1: Basic Natural Language Processing on News Title to classify Stock Trend
#### Main question: 
Dose news a "real" indicator for security market? Is there real relation between financial news and market movement?

#### Date: 
30 Oct 2020 (HKT/ GMT +8)

#### Detailed description: 
This mini project is to perform a classification task to the sp500 movement based on financial news. We restructure the dataset by combining all news released in the same day as one observation associated with the same day log return from sp500. 2 classes are formed with criteria of larger or equal to 0then definded as UP and DOWN. We employ a simple n-grams td-idf statistics to convert news into numeric factors after performing special preprocessing on Natural Language including case lowering, punctation and non-alphabetic symbol removal, stop word removal, tokenization and word lemmatization, and reduce the dimension by limiting the acceptance range of these td-idf, the exact acceptance range vary from models, and we treat it as a hyperparameter to turn. XGBoost are then employed for finding the relation between the processed features and the daily benchmark's log return. The validation AUC is used to evaluate the model performance for different setting of hyperparameters and the best models are selected and applied to the test set.

#### Finding and achievement: 
The 1 gram, 2 grams and 3 grams models have testing performance of 57.3, 68.2, 61.4 AUC respectively. Ensemble model from them further achieve a testing performance of 0.690 AUC. It shows the relation between financial news and the market. 

#### Possible improvement: 
1. Obviously, the n-grams td-idf is a naive approach and one is expected to obtain better result by using advanced NLP technique such as word embedding (Word2Vec, Glove) or transformer-based model (BERT, etc). 
2. A "training-validation-testing" approach is used, and the testing performance is a point estimator instead. One should apply walking forward or even sequential bootstrapped walking forward to obtain a more accurate testing performance.
3. Security pricing is indeed a sequential data. One can apply sequential model such as RNN/ LSTM/ transformer model which capture the delay effect on news. 
4. Although the result shows its relation, we need to clarify whether this is a leading or lagging indicator! Only leading indicator are worth included into the final model!
5. The significance of news are expected to be different among news. A better approach combining them with different weights maybe useful. 

#### Data: 
News: "Daily Financial News for 6000+ Stocks", the data was scraped from benzinga.com. Big Thanks to bot_developer. The news articles are the property of Benzinga. https://www.kaggle.com/miguelaenlle/massive-stock-news-analysis-db-for-nlpbacktests 

Price: Yahoo finance for sp500

#### License: 
CC0: Public Domain

#### Last Update: 
15 Jun 2021

