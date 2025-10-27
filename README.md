# LLM-Bias-Mapping

## Overview
This project investigates how large language models (LLMs) respond to politically sensitive prompts, with a focus on U.S. domestic issues such as:

- Gun Control
- Climate Change
- Taxation & Wealth Redistribution
- Policing & Criminal Justice Reform

## Methodology
Prompt Design:
Each topic was tested using three framing styles:

- Balanced: neutral and factual
- Party Framing: uses language typical of Democratic or Republican narratives
- Controversy: emotionally charged or polarized phrasing

Response Collection: 
Prompts were batch-submitted to GPT-4, generating 12 responses per prompt. Each response was stored with metadata in gpt4_responses.csv.

Bias Labeling:
A keyword-based approach classified responses as Left, Right, or Neutral depending on detected ideological terms (e.g., “systemic racism,” “law and order,” etc.).

Sentiment Analysis:
VADER Sentiment Analyzer scored responses between –1 (negative) and +1 (positive) to assess emotional charge.

Classifier Training:
A Logistic Regression model using TF-IDF vectorization was trained to automate bias detection (train/test split 80/20).

## Key Findings
- Prompt framing matters. Controversial language increased both ideological polarization and emotional negativity.
- Topic sensitivity. “Policing and Criminal Justice Reform” responses leaned left; “Gun Control” and “Taxation” were more balanced.
- Emotional intensity. Controversial prompts consistently generated more negative sentiment.
- Overall distribution. Most responses were neutral, but left-leaning outputs were more frequent than right-leaning ones.
Together, bias labeling and sentiment analysis revealed that framing affects not only what models say, but how they say it.

Link To Colab Notebook: https://colab.research.google.com/drive/1NKMY4Boydjg2abRRsV5r2EkCbC0_NVpc?usp=sharing
Please note you will need to paste in your own API Key. 
