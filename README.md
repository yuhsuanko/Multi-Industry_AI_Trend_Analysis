# Multi-Industry_AI_Trend_Analysis

## Overview

This project analyzes over **200,000 AI-related news articles (2022–2025)** to understand how artificial intelligence is transforming industries, affecting job roles, and influencing public sentiment across time.

## Key Findings

- **Industries Most Affected**: Technology, finance, and healthcare are undergoing both high adoption and disruption.
- **Jobs at Risk**: Repetitive knowledge-based roles (e.g., teaching, law) show increasing automation risk, while empathetic and design-heavy roles (e.g., UX, nursing) are more resilient.
- **Trend Drivers**: Tools like ChatGPT, Bard, and Generative AI sparked sentiment shifts in early 2023.
- **Global Focus**: The US and India dominate AI-related discourse, especially in policy and innovation.
- **Need for Action**: Rapid deployment of AI necessitates governance, reskilling, and cross-sector collaboration.

## Data Summary

- **Time Period**: Jan 2022 – Apr 2025  
- **Sources**: News aggregators, media outlets, financial press  
- **Size**: 200,083 raw articles → 185,916 clean articles  
- **Columns**: `url`, `date`, `title`, `text`, `language`

## Pipeline Components

### Text Cleaning

- Removed boilerplate, HTML, dates, non-ASCII characters, and junk tokens
- Applied SpaCy lemmatization and stopword filtering

### Topic Modeling

- Embedding: `all-MiniLM-L6-v2` (Sentence Transformers)  
- Dimensionality Reduction: UMAP  
- Clustering: HDBSCAN  
- Keyword Extraction: CountVectorizer + TF-IDF  
- Labeling: KeyBERT-inspired + zero-shot classification (`facebook/bart-large-mnli`)  
- Output: 578 topics grouped into 13 industries

### Named Entity Recognition

Used SpaCy NER to extract:
- Top People: Elon Musk, Sam Altman, Joe Biden, etc.
- Top Organizations: OpenAI, Google, Microsoft, etc.
- Top Technologies: ChatGPT, Bard, Vision Pro, etc.

### Sentiment Analysis

- Labeled: 500 samples using GPT-4 and lexicons  
- Model: Fine-tuned `bert-base-uncased`  
- Classes: Positive, Neutral, Negative  
- Accuracy: 71% (Macro F1: 0.68)

### Temporal and Industry Trends

Visualized sentiment trajectories for:
- Industry (e.g., Technology, Government, Manufacturing)
- Job Role (e.g., Financial Analyst, Project Manager)
- Entity (e.g., OpenAI, Elon Musk, USA, China)

## Visualizations

Visualizations include:
- Sentiment over time
- Topic distribution by industry
- Entity-level sentiment trends

## Actionable Insights

- **For Companies**: Adopt AI to augment—not replace—human work; invest in reskilling.
- **For Academia**: Integrate AI ethics and applied AI modules into curricula.
- **For Policymakers**: Build national AI governance frameworks and public infrastructure.

## Tech Stack

- Python, Pandas, SpaCy, Scikit-learn, HuggingFace Transformers  
- BERTopic, UMAP, HDBSCAN, BERT, KeyBERT, GPT-4  
- Matplotlib, Seaborn
