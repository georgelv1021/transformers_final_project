# Leveraging NLP to Derive Investment Signal(s) from News Articles

In this project, we propose an innovative approach that combines the power of natural language processing 
(NLP) and network science to analyze news articles. The project's main objective is to automatically 
derive investment signals from news articles and assess their impact on associated companies. By 
leveraging NLP models specifically fine-tuned for this purpose, we aim to gain insights into how they affect companies/assets across diverse industries. 


## Table of Contents  
1. [Overview](#Overview)  
2. [Data](#data)
4. [Modeling](#modeling)
5. [Inferencing](#Inferencing)

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

---
## Modeling


Model Card: https://huggingface.co/yiyanghkust/finbert-tone?text=growth+is+strong+and+we+have+plenty+of+liquidity

---
## Inferencing

This project leverages the sentiment scores generated from the FinBERT model to devise financial strategies aimed at achieving promising expected returns on selected stocks. Utilizing the AlphaLens package, we analyze sentiment scores as a predictive factor for stock performance across three distinct time horizons: 1, 5, and 10 quarters. This analysis helps provide investors with insights into potentially profitable investments as well as those that may be less favorable. The objective is to equip investors with a nuanced understanding of how sentiment influences stock performance, thereby guiding more informed investment decisions.

<img width="464" alt="Screenshot 2024-04-14 at 3 29 59 PM" src="https://github.com/georgelv1021/transformers_final_project/assets/57245683/a5d4e537-d453-4e3f-97a6-9db58702c96f">
<img width="467" alt="Screenshot 2024-04-14 at 3 31 45 PM" src="https://github.com/georgelv1021/transformers_final_project/assets/57245683/17417acb-6bd6-4539-95bf-785a16ae4516">


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

    

   

