---
layout: page
title: Indicina — AI Credit Scoring
permalink: /10_startup_indicina
---
## Indicina — AI-Driven Credit Scoring, Nigeria

<img src="images/10_startup_indicina.jpg?raw=true"/>

---

Served as an analytics engineering consultant for Indicina, a credit-scoring startup based in Nigeria. The core deliverable was the "Decide" model — an AI-driven credit scoring system that evaluates small businesses using bank statement transaction data and merchant records. The model combines NLP-based transaction segmentation with predictive AI to generate forward-looking credit scores, addressing a critical gap in financial inclusion for underbanked small businesses.

**1. Segment transactions using NLP models**

Built NLP pipelines to ingest raw bank statement text and automatically categorize each transaction into meaningful segments — payroll, rent, utilities, merchant income, etc. Accurate segmentation is the foundation on which the entire scoring model depends.

```python
# Example: Transaction segmentation with keyword-based NLP
import pandas as pd

CATEGORIES = {
    "income": ["salary", "payroll", "transfer in", "deposit", "revenue"],
    "rent": ["rent", "lease", "landlord"],
    "utilities": ["electric", "water", "internet", "airtime"],
    "merchant": ["pos", "merchant", "sale", "invoice"],
}

def segment_transactions(df: pd.DataFrame, desc_col="description") -> pd.DataFrame:
    def classify(text):
        text_lower = text.lower()
        for cat, keywords in CATEGORIES.items():
            if any(kw in text_lower for kw in keywords):
                return cat
        return "other"

    df["category"] = df[desc_col].apply(classify)
    return df
```

**2. Build predictive scenario models for future transactions**

After segmentation, trained AI models to project likely future transaction patterns for each business. These scenarios inform the credit score by estimating a borrower's capacity to repay under various economic conditions — not just their historical behavior.

```python
# Example: Simple transaction forecasting skeleton
from sklearn.linear_model import Ridge
import numpy as np

def forecast_monthly_income(history: np.ndarray, horizon: int = 3) -> np.ndarray:
    X = history[:-1].reshape(-1, 1)
    y = history[1:]
    model = Ridge(alpha=1.0)
    model.fit(X, y)
    forecasts = []
    last = history[-1]
    for _ in range(horizon):
        pred = model.predict([[last]])[0]
        forecasts.append(pred)
        last = pred
    return np.array(forecasts)
```

**3. Generate composite credit scores for small businesses**

Combined the segmented transaction features and forward-looking scenario outputs into a single interpretable credit score. The scoring engine was designed to be explainable — flagging the key factors driving each decision — so that both the platform and the end borrower understand the outcome.

**4. Integrate with merchant transaction data**

Extended the model beyond bank statements to incorporate merchant-side transaction records. This dual-source approach provided a richer and more reliable signal, particularly for businesses that operate primarily through point-of-sale or invoice-based revenue.

For more details see [LinkedIn](https://www.linkedin.com/in/pramodmisra/) | [GitHub](https://github.com/pramodmisra)
