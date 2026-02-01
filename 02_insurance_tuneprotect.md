---
layout: page
title: MDM & Cloud Data Warehouse Migration
permalink: /02_insurance_tuneprotect
---
## MDM & Cloud Data Warehouse Migration — Tune Protect Insurance, APAC

<img src="images/02_insurance_tuneprotect.jpg?raw=true"/>

---

Led the full master data management (MDM) implementation and on-premise-to-cloud data warehouse migration for Tune Protect, a $260M market-cap insurance company in Southeast Asia. The project spanned underwriting, sales, and marketing functions, requiring deep collaboration between business stakeholders and technology teams to deliver a single source of truth.

**1. Build the data dictionary and map data points across applications**

Worked with business teams across underwriting, sales, and marketing to define every critical data element. Mapped data points from multiple source applications into a unified schema, resolving naming conflicts and aligning definitions across departments.

```python
# Example: Data dictionary builder
import pandas as pd

def build_data_dictionary(source_schemas: dict) -> pd.DataFrame:
    rows = []
    for source, columns in source_schemas.items():
        for col in columns:
            rows.append({
                "source_system": source,
                "column_name": col["name"],
                "data_type": col["type"],
                "nullable": col.get("nullable", True),
                "description": col.get("desc", ""),
                "mapped_to": col.get("target", "")
            })
    return pd.DataFrame(rows)
```

**2. Execute on-premise to cloud migration**

Migrated the entire data warehouse from an in-house on-premise setup to a cloud-based platform. Ensured zero data loss through staged migration with full reconciliation checks at each phase.

**3. Deploy CRM-ready analytics in Power BI**

After migration, collaborated with function heads to design and deliver tailored Power BI dashboards — daily, weekly, and monthly — for each vertical. The new reporting layer enabled CRM campaigns to achieve over 50% efficacy, a significant uplift from the prior baseline.

```python
# Example: Post-migration reconciliation check
def reconcile(source_df, target_df, key_col, check_cols):
    merged = source_df.merge(target_df, on=key_col, how="outer", suffixes=("_src", "_tgt"), indicator=True)
    mismatches = merged[merged["_merge"] != "both"]
    for col in check_cols:
        diff = merged[merged[f"{col}_src"] != merged[f"{col}_tgt"]]
        print(f"{col}: {len(diff)} mismatches")
    print(f"Unmatched rows: {len(mismatches)}")
    return merged
```

**4. Build conceptual data models and primary key framework**

Defined primary keys across all entities, then constructed high-level conceptual data models. These models were tested, deployed, and rolled out to the broader team as the foundation for ongoing analytics.

For more details see [LinkedIn](https://www.linkedin.com/in/pramodmisra/) | [GitHub](https://github.com/pramodmisra)
