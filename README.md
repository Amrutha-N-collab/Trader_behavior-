# Trader_behavior-
Crypto Trader Sentiment & Profitability Model
 Project Overview

This project analyzes cryptocurrency trader behavior by combining:

Historical trade execution data

Market sentiment classification

Behavioral performance metrics

The objective is to:

Understand how sentiment influences trading outcomes

Predict the probability of a trade being profitable

Identify distinct trader behavioral archetypes

The final output includes a predictive machine learning model and an interactive Streamlit dashboard.

 Dataset Description

The dataset contains:

Trade-level information (price, size, direction, timestamp)

Trader account identifiers

Realized PnL (closed_pnl)

Sentiment classification (Fear, Greed, Extreme Greed, Neutral)

Target variable:

profitable (1 if trade PnL > 0, else 0)

 Data Processing & Feature Engineering

Key preprocessing steps:

Timestamp alignment and sorting by trader and time

Creation of binary profitability indicator

Rolling behavioral features:

Rolling win rate (last N trades)

Rolling average trade size

Rolling PnL volatility

One-hot encoding of:

Market sentiment

Trade direction

Coin groups

Missing values were handled using appropriate numeric coercion and imputation.

 Exploratory & Statistical Analysis

We evaluated:

Profitability distribution across sentiment categories

Relationship between volatility and trade outcomes

Behavioral consistency patterns across traders

Statistical testing was used to assess whether sentiment significantly affects profitability.

 Predictive Modeling
Objective:

Predict the probability that the next trade will be profitable.

Model Used:

Random Forest Classifier

Features:

Trade size

Rolling win rate

Rolling volatility

Sentiment indicators

Direction indicators

Evaluation Metric:

ROC-AUC Score

Final ROC-AUC: (insert your actual score here)

The model demonstrates meaningful predictive power in distinguishing profitable vs non-profitable trades.

 Economic Validation

Model probabilities were evaluated for economic significance:

High-probability trades showed higher realized returns.

Low-probability trades underperformed.

This suggests that the model provides actionable trading insight beyond statistical accuracy.

 Trader Clustering (Behavioral Segmentation)

KMeans clustering (3 clusters) was applied on trader-level aggregated features:

Average trade size

Mean PnL

PnL volatility

Win rate

This revealed distinct trader archetypes:

Consistent Professionals – High win rate, lower volatility

High-Risk Whales – Large trade sizes, high volatility

Retail/Noise Traders – Lower win rate, smaller positions

Clustering enhances understanding of behavioral differences in trading performance.

 Streamlit Dashboard

An interactive dashboard was built to:

Predict trade profitability probability

Visualize trader cluster distributions

Display cluster summary statistics

Run Locally:
pip install -r requirements.txt
python -m streamlit run app.py
 Key Takeaways

Market sentiment has measurable impact on trading outcomes.

Behavioral features improve predictive accuracy.

Traders can be meaningfully segmented into performance archetypes.

Machine learning can provide forward-looking profitability signals.
