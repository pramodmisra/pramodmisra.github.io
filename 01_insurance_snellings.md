---
layout: page
title: Enterprise Data & AI Transformation
permalink: /01_insurance_snellings
---
## Enterprise Data & AI Transformation — Snellings Walters Insurance Agency

<img src="images/01_insurance_snellings.jpg?raw=true"/>

---

As Director of Data Analytics & AI Automation at Snellings Walters Insurance Agency, I am leading enterprise-wide data and AI transformation initiatives. The engagement spans strategy design, end-to-end execution, and building high-performing analytics teams — all within a regulated, high-stakes insurance environment where data quality and governance are non-negotiable.

**1. Define the enterprise AI & analytics strategy**

The first phase focused on aligning business objectives with data and AI capabilities. This involved auditing existing data pipelines, cataloguing available datasets, and mapping capability gaps against the organization's growth roadmap.

```python
# Example: Automated data-source inventory scanner
import pandas as pd
import os

def scan_data_sources(directory):
    sources = []
    for root, dirs, files in os.walk(directory):
        for f in files:
            if f.endswith(('.csv', '.xlsx', '.parquet', '.json')):
                path = os.path.join(root, f)
                size_kb = os.path.getsize(path) / 1024
                sources.append({"file": f, "path": path, "size_kb": round(size_kb, 2)})
    return pd.DataFrame(sources)
```

**2. Build and scale the analytics & AI team**

Recruited and structured a cross-functional analytics team. Established clear ownership across data engineering, ML model development, and business intelligence to ensure scalable delivery.

**3. Implement AI-driven automation for core insurance workflows**

Deployed ML models targeting underwriting efficiency, claims triage, and risk scoring. Each model was validated against historical outcomes before production rollout, with continuous monitoring in place.

```python
# Example: Risk-score pipeline skeleton
from sklearn.ensemble import GradientBoostingClassifier
from sklearn.model_selection import train_test_split

def train_risk_model(df, target_col="claim_flag"):
    features = [c for c in df.columns if c != target_col]
    X_train, X_test, y_train, y_test = train_test_split(
        df[features], df[target_col], test_size=0.2, random_state=42
    )
    model = GradientBoostingClassifier(n_estimators=200, max_depth=4)
    model.fit(X_train, y_train)
    print(f"Test accuracy: {model.score(X_test, y_test):.3f}")
    return model
```

**4. Establish data governance and reporting standards**

Built data dictionaries, enforced schema validation across upstream feeds, and delivered executive-level dashboards in Power BI — enabling data-driven decision making at every level of the organization.

For more details see [LinkedIn](https://www.linkedin.com/in/pramodmisra/) | [GitHub](https://github.com/pramodmisra)
