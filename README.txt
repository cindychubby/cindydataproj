# Germany Hourly Power Generation Project

Files:
- `Germany_Power_Generation_Analysis_and_Thermal_Forecast.ipynb`: end-to-end notebook.
- `germany_hourly_generation_long.csv`: synthetic long-format source data.
- `germany_hourly_generation_wide.csv`: synthetic wide-format subcategory data.

The dataset is synthetic and intended for practice. It contains 2 years of hourly observations (2023-01-01 through 2024-12-30 23:00), with categories:
Thermal, Water, Wind, Nuclear, Solar.

Thermal subcategories: Lignite, Hard Coal, Natural Gas, Oil, Biomass, Rubbish.
Water: Run-of-River, Reservoir, Pumped Storage.
Wind: Onshore Wind, Offshore Wind.
Nuclear: Nuclear.
Solar: Solar.

Run the notebook with the working directory set to this folder. Dependencies:
pandas, numpy, matplotlib, scipy, statsmodels, scikit-learn.


I completed both my undergraduate and master's studies at Shanghai Jiao Tong University. I pursued a dual degree in Finance and Computer Science as an undergraduate, with a minor in Statistics, and majored in Financial Engineering for my master's degree.
Probability, ml; software development; foundamentals of finance
have provided me with a solid foundation.
Interest
Two aspects
5min bar data
Feature engineering – modelling
I initially spent a lot of time on feature engineering, but later realized that powerful models can learn a lot from temporal and cross-sectional attention when sufficient data is available. So I've also started exploring model research. However, I still believe factor engineering is important for noise reduction and can simplify the modeling process.
At first focus on feature part, researched on market microstructure:
characterize how different market participants react to market events, such as mid-price movements
depict imbalance & resilience
large order clustering

examined whether the imbalance at the best bid and ask differed from the imbalance across deeper levels
--imb
slope不够好
maintain a rolling order book profile, compared current conditions with long-term patterns, and modeled near-, mid-, and far-depth structural imbalances across different levels.
Large-Order Clustering
Large order
estimate conditional prob of observing a large trade following a large trade, compared it with the unconditional probability to measure large-order clustering.
Further research transition probabilities between large vs small; decompose into buy sell; arrival intensity / time gap between large orders

10s forecast
A high IC is not necessarily meaningful, because the signal may only perform well when prices are close to zero or market liquidity is poor, where actual trading opportunities are limited. I noticed that fewer than 10% of my signal actually resulted in trades, and most trades occurred during periods of high volatility. 
So I wanted to build a tradeability indicator to identify when market conditions were more favorable for execution.
estimated fill probabilities of passive order on best bid/ask
vol
price impact 
I then combined these features into a score between zero and one, which could be used as a weight in evaluating the signal through weighted IC.
The goal was to focus more on periods with genuine trading opportunities rather than treating all observations equally.



