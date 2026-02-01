---
layout: page
title: Big Data Analytics & Business Intelligence
permalink: /07_telecom_vodafone
---
## Big Data Analytics & Business Intelligence — Vodafone

<img src="images/07_telecom_vodafone.jpg?raw=true"/>

---

Served as General Manager at Vodafone, leading analytics and business intelligence initiatives across global telecom operations. Over 20 years of hands-on experience in data analytics informed a strategic approach to deploying big data at scale — from recommendation engines and churn reduction models to NPS modelling and ML deployment across production environments. Spoke at TMForum on the practical pitfalls and opportunities of big data in telcos.

**1. Deploy ML models at scale across production systems**

Designed and deployed machine learning models into live telecom environments, including recommendation engines and customer churn prediction. Each model was built with production constraints in mind — latency, throughput, and monitoring from day one.

```python
# Example: Churn prediction pipeline
from sklearn.ensemble import RandomForestClassifier
from sklearn.metrics import classification_report
import pandas as pd

def build_churn_model(df: pd.DataFrame, target="churned"):
    features = [c for c in df.columns if c != target]
    X, y = df[features], df[target]
    model = RandomForestClassifier(n_estimators=300, max_depth=10, random_state=0)
    model.fit(X, y)
    preds = model.predict(X)
    print(classification_report(y, preds))
    return model
```

**2. Build NPS modelling and customer insight frameworks**

Developed end-to-end NPS (Net Promoter Score) modelling pipelines that connected survey responses to operational data — enabling the business to identify the specific touchpoints driving customer satisfaction or dissatisfaction.

**3. Drive churn reduction through predictive analytics**

Built and iterated on churn-reduction models that flagged at-risk customers before contract expiry. These models were integrated into CRM workflows, allowing sales and retention teams to act on predictions in real time.

```python
# Example: At-risk customer flagging
def flag_at_risk(customers: pd.DataFrame, model, threshold=0.6) -> pd.DataFrame:
    scores = model.predict_proba(customers.drop(columns=["customer_id"]))[:, 1]
    customers["churn_score"] = scores
    customers["at_risk"] = customers["churn_score"] >= threshold
    return customers[customers["at_risk"]].sort_values("churn_score", ascending=False)
```

**4. Present insights at industry forums**

Spoke at TMForum in France on the strategic use of big data in telecoms, covering common pitfalls — data silos, governance gaps, and over-engineering — and practical paths to value extraction.

For more details see [LinkedIn](https://www.linkedin.com/in/pramodmisra/) | [Mobile World Live Coverage](https://www.mobileworldlive.com/featured-content/top-three/vodafone-idea-exec-highlights-big-data-pitfalls) | [GitHub](https://github.com/pramodmisra)
