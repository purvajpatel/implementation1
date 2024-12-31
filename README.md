# Research Overview / Motivation
This implements the paper "Generalized Distrubition Prediction for Asset Returns" by Isak Petursson and Maria Oskarsdottir. The model leverages Long Short-Term Memory to predict the distrbution of Asset Returns.

Accurately modeling the disbution of returns is a cornerstone to risk management and portfolio optimization. Traditional approaches assume normality in both return and volatility distrubtions, which can lead to inaccurate results due to a certain level of randomness and skewness in actual financial data. The paper aims to general asset return prediction to create a robust, asset-netural (meaning it can work for a variety of asset types including stocks, commodities, and cryptocurrencies) framework that can handle diverse classes and market conditions.

# Architecture
The implementation uses a two-stage model architecture:

1. Asset-Specific Prediction - LSTMs use asset-specific features to predict the normalized asset returns

2. Market Data Scaling - Broader market conditions refine the predictions via another LSTM layer

# Advantages / Disadvantages
Advantages
-
Robust handling of diverse assets, improved accuracy compared to linear regression and dense neural networks, and is scalable to new asset classes and market data

Disadvantages
-
Computationally expensive due to LSTM training, and is very sensitive to parameters like dropout, sequence length, and learning rate.

# Novelty + Key Takeaways
1. Asset-Neutral Features - Genetalized input representation allows the code to be applied across different asset types

2. Two-Stage Approach - Combines the asset-specific and market-wide insights for improved preditions. This means that specific volatiltiy in certains types of markets, like the commoditiy market, can be tracked as well as general events that might impact the entire market.

# Results
1. Results of the S&P 500 at the median quantile
  ![image](https://github.com/user-attachments/assets/36a49b26-598f-43f5-9acf-9800d916f747)
2. Results of Cryptocurrencies (Bitcoin) at the median quantile 
![outputbitcoin](https://github.com/user-attachments/assets/ffee22af-79ac-433c-ac8c-3d4329792e7f)


