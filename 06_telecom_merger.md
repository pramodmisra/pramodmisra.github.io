---
layout: page
title: Database Merger & AWS Cloud Migration
permalink: /06_telecom_merger
---
## Database Merger & AWS Cloud Migration

<img src="images/06_telecom_merger.jpg?raw=true"/>

---

Spearheaded the merger of two large corporate databases — from companies with $1.8B and $1.2B market capitalizations respectively — into a single unified database on AWS cloud. The engagement covered complete documentation, data mapping, migration execution, and post-migration validation. The project was delivered a full month ahead of the set timeline and received formal recognition for successful completion.

**1. Document and map data across both organizations**

Collaborated with business and technology teams on both sides to produce a comprehensive data map. Every table, key relationship, and transformation rule was documented before a single row was moved — critical given the scale and complexity of merging two independently operated systems.

```python
# Example: Cross-org table-level mapping tracker
import pandas as pd

def build_merge_map(org_a_tables: list, org_b_tables: list) -> pd.DataFrame:
    rows = []
    for t in org_a_tables:
        match = next((b for b in org_b_tables if b["logical_name"] == t["logical_name"]), None)
        rows.append({
            "logical_name": t["logical_name"],
            "org_a_table": t["physical_table"],
            "org_b_table": match["physical_table"] if match else "NO MATCH",
            "columns_a": t["col_count"],
            "columns_b": match["col_count"] if match else 0,
            "status": "mapped" if match else "orphan"
        })
    return pd.DataFrame(rows)
```

**2. Align definitions and create data flow diagrams**

Worked with cross-functional teams to harmonize conflicting business definitions between the two organizations. Built end-to-end data flow diagrams and process maps for each function to ensure clarity before migration began.

**3. Execute migration and run UAT**

Performed the staged migration to AWS, then worked with key stakeholders to run user acceptance testing on all critical reports and dashboards. Every output was reconciled against the source systems before sign-off.

**4. Deliver ahead of schedule**

The entire migration — documentation, mapping, execution, and validation — was completed one month before the deadline. The early delivery was driven by disciplined planning, clear ownership, and continuous stakeholder communication throughout.

For more details see [LinkedIn](https://www.linkedin.com/in/pramodmisra/) | [GitHub](https://github.com/pramodmisra)
