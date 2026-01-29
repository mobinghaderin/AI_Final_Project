# financial-news-price-reaction

End-to-end pipeline for financial news–driven intraday stock movement prediction:

- Collects financial news (Yahoo Finance RSS)
- Aligns each news timestamp to an intraday return window (5–30 minutes)
- Labels direction classes using ±0.1% threshold: down / neutral / up
- Text preprocessing (sentence split, tokenization, stopwords, lemmatization)
- Sentiment features: FinBERT + VADER
- Models: LSTM, Transformer (DistilBERT), Hybrid Attention-LSTM
- Training: Adam optimizer, LR grid search, cross-validation
- Metrics: Accuracy, F1-macro, Confusion Matrix, ECE (calibration)

> If real data fails (no 1m prices available, RSS issues, etc.), it automatically falls back to a synthetic dataset to produce reasonable output.

## Quickstart

### 1) Create environment & install
```bash
python -m venv .venv
source .venv/bin/activate  # (Windows: .venv\Scripts\activate)
pip install -r requirements.txt
pip install -e .
