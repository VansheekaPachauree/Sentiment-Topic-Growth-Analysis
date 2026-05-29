# Sentiment, Topic, and Growth Analysis — iPhone 3GS Launch (2009)

Multi-stage NLP pipeline applied to 21,269 Apple-related tweets from the
Sentiment140 dataset, covering the iPhone 3GS launch period (Apr–Jun 2009).
Full write-up: `Report_Sentiment_Topic_Growth_iPhone3GS.pdf`.

## Pipeline
1. `1_data_preparation.ipynb` — Sentiment140 ingestion, cleaning, Apple keyword filter (47 terms)
2. `2_sentiment_relabelling.ipynb` — Sentiment relabelling with CardiffNLP twitter-RoBERTa (45% of labels revised)
3. `3_topic_modelling.ipynb` — Topic modelling with LDA (perplexity-tuned) and BERTopic (coherence-tuned, all-mpnet-base-v2 + UMAP + HDBSCAN)
4. `4_novelty_and_growth.ipynb` — LDA topic-space cosine novelty detection, topic growth, and sentiment shift analysis

## Key finding
The iPhone 3GS launch did not introduce new discourse — it amplified pre-existing topics and made them more negative. The iPhone OS 3.0 update topic grew from 12 to 227 tweets (95% post-launch share) with a 43-percentage-point increase in negativity.

## Stack
Python, pandas, scikit-learn, HuggingFace Transformers, BERTopic, sentence-transformers, UMAP, HDBSCAN, gensim, NLTK, matplotlib, seaborn, wordcloud

## Note
Notebooks were developed in Google Colab; data flows between stages via Google Sheets exports. The relabelled corpus is loaded from a local xlsx export in stage 2 for faster reloads.