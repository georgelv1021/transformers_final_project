# Leveraging Finbert Model for Building Portfolio

In this project, we propose an innovative approach that combines the power of natural language processing 
(NLP) and network science to analyze news articles. The project's main objective is to automatically 
derive investment signals from news articles and assess their impact on associated companies. By 
leveraging NLP models specifically fine-tuned for this purpose, we aim to gain insights into how they affect companies/assets across diverse industries. 


## Table of Contents  
1. [Overview](#Overview)  
2. [Data](#data)
4. [Modeling](#modeling)
5. [Critical Analysis](#critical-analysis)
6. [Inferencing](#Inferencing)

---
## Overview

FinBERT is a specialized adaptation of the popular BERT model, which itself is a breakthrough in natural language processing introduced by Google. BERT models are designed to pre-train on a large corpus of text and then fine-tuned for specific tasks. FinBERT specifically targets the financial sector.

Key Points for FinBERT:

- **Domain Specificity**: Unlike generic BERT models, FinBERT is trained on financial texts. This enables it to better understand the nuances and jargon of financial news, reports, and documents.

- **Sentiment Analysis**: One of the primary uses of FinBERT is to assess the sentiment of financial texts. It can classify sentiments as positive, neutral, or negative, which are crucial for financial decision-making and analysis.

- **Impact Prediction**: Beyond mere sentiment, FinBERT can predict the potential impacts of financial events or statements on a company's performance, market reputation, and other financial metrics.

Goals:
1. Identify causal event(s) mentions in news articles and analyze their impact to associated companies
2) Apply and fine-tune NLP models to recognize causal language 
connecting event pairs and their impact to companies
3) Derive and backtest investment signal(s)
4) Represent events and causal links as a graph using graph theory methods and extract causal event chains and subgraphs from the overall graph.

---

## Data

Our dataset comprises stock price data for S&P 500 companies, covering the period from September 12, 2022, to September 13, 2023. In addition to stock prices, the dataset includes associated news articles that may have directly or indirectly influenced these prices. For each news item, the dataset provides the publication date, title, content, and the ticker symbols of the relevant companies. This comprehensive compilation of financial and media data is structured to facilitate analysis of the impact of news on stock market behavior.
![alt text](image.png)

---
## Modeling

Model Card: https://huggingface.co/yiyanghkust/finbert-tone?text=growth+is+strong+and+we+have+plenty+of+liquidity

Step 1: Application of FinBERT Pipeline


Tokenization

- **Tokenizer**: This is the first step in the FinBERT pipeline. The tokenizer takes the text from the `title_content` column and breaks it down into tokens that BERT can understand. These tokens include individual words, punctuation, and subword units for words that BERT hasn't seen before.

- **Token IDs & Attention Mask**: Each token is converted into a unique integer (token ID). Along with this, an attention mask is created to tell the model which tokens are meaningful and which are padding.

Model Processing

- **FinBERT Model**: The token IDs and attention masks are then fed into the FinBERT model. FinBERT, as a BERT model variant, contains multiple layers of Transformer units, which are designed to process sequences of text data. It processes the text in the context of each token, capturing the nuances of the language used in financial news.

- **Sentiment Classification**: The FinBERT model has been fine-tuned to classify the sentiment of financial text. This means that during its training, it learned to associate certain patterns in the tokenized text with sentiment labels (such as positive, neutral, and negative).

- **Output**: For each piece of text, FinBERT outputs a set of logits, which are raw, non-normalized predictions that a machine learning model generates in its last layer. These logits are transformed into probabilities through a softmax function, where the highest probability corresponds to the predicted sentiment.

Step 2: Sentiment Analysis Results

- **Sentiment**: This column in the results represents the sentiment of the article as predicted by FinBERT.

- **Sentiment Score**: This column represents the confidence score of the sentiment prediction. The model outputs a score, often close to 1 for high confidence in its prediction. For instance, a score of 0.999993 for negative sentiment means the model is almost certain the article has a negative sentiment.

![alt text](image-2.png)

---

## Critical Analysis

**What needs to be improved for this model?**

This model excels at performing sentiment analysis on sentences or articles that explicitly mention a company's name, but it is less effective for analyzing external factors that are crucial for predicting a company's stock performance.

**Solution**: Ensemble method.

---

## Inferencing

Next, we can leverage the sentiment scores generated from the FinBERT model to devise financial strategies aimed at achieving promising expected returns on selected stocks. Utilizing the AlphaLens package, we analyze sentiment scores as a predictive factor for stock performance across three distinct time horizons: 1, 5, and 10 quarters. This analysis helps provide investors with insights into potentially profitable investments as well as those that may be less favorable. The objective is to equip investors with a nuanced understanding of how sentiment influences stock performance, thereby guiding more informed investment decisions.

<img width="403" alt="Screenshot 2024-04-16 at 8 21 29 PM" src="https://github.com/georgelv1021/transformers_final_project/assets/57245683/8f293ec8-5b9e-429a-907e-3debe14c7bdc">
<img width="1004" alt="Screenshot 2024-04-16 at 8 21 48 PM" src="https://github.com/georgelv1021/transformers_final_project/assets/57245683/d4cba5ba-36e4-47ca-9b4b-724867da6a03">


---

## Video Recording

Links to be added

---
## Resource
1. Andrew Chin and Yuyu Fan “Leveraging Text Mining to Extract Insights from Earnings Call 
Transcripts,” Journal Of Investment Management, Vol. 21, No. 1, (2023), pp. 81–102
2. https://github.com/shahrukhx01/multitask-learning-transformers   
3. https://www.analyticsvidhya.com/blog/2023/06/building-a-multi-task-model-for-fake-and-hate-probability-prediction-with-bert/
4. Price, Chris. "Estimating Causal Effects on Financial Time-Series with Causal Impact BSTS." 
Towards Data Science. January 29, 2020.
5. https://github.com/shahrukhx01/multitask-learning-transformers   
6. https://www.analyticsvidhya.com/blog/2023/06/building-a-multi-task-model-for-fake-and-hate-probability-prediction-with-bert/
7. https://snap.stanford.edu/class/cs224w-2023/   

    

   

