---
layout: page
title: Report Migration & Cross-Timezone Documentation
permalink: /05_pharma_migration
---
## Report Migration & Cross-Timezone Documentation — Global Pharma Company

<img src="images/05_pharma_migration.jpg?raw=true"/>

---

Led the report migration, data process mapping, and end-to-end documentation effort for one of the largest global pharmaceutical companies. The work spanned teams across three different time zones, demanding tight coordination, clear communication protocols, and meticulous quality control to ensure nothing fell through the cracks during the transition.

**1. Build existing definitions and map data variables to cost elements**

Worked with teams across geographies to catalogue every data variable in use, map each one to the relevant cost elements in the reporting structure, and document the relationships. This became the single source of truth for the migration.

```python
# Example: Cross-timezone variable mapping export
import pandas as pd
from datetime import datetime

def export_variable_map(mappings: list, output_path: str):
    df = pd.DataFrame(mappings, columns=[
        "variable_name", "source_system", "cost_element",
        "data_type", "owner_timezone", "last_validated"
    ])
    df["exported_at"] = datetime.utcnow().isoformat()
    df.to_excel(output_path, index=False)
    print(f"Exported {len(df)} mappings → {output_path}")
```

**2. Create data flow diagrams and process maps**

Produced detailed data flow diagrams for each reporting function — showing source systems, transformation logic, and final outputs. These were designed for end users, not just engineers, so clarity and accessibility were prioritized.

**3. Deliver end-to-end quality control on existing data**

Ran systematic QC across all data points before and after migration. Caught and resolved discrepancies in aggregation logic, date handling, and currency conversions — issues that commonly surface in multi-region pharma environments.

```python
# Example: Multi-region QC summary
def qc_summary(regions: dict) -> pd.DataFrame:
    rows = []
    for region, checks in regions.items():
        rows.append({
            "region": region,
            "total_checks": len(checks),
            "passed": sum(1 for c in checks if c["status"] == "pass"),
            "failed": sum(1 for c in checks if c["status"] == "fail"),
            "pass_rate": f"{sum(1 for c in checks if c['status'] == 'pass') / len(checks):.1%}"
        })
    return pd.DataFrame(rows)
```

**4. Create "how-to" guides for critical roles**

Authored a set of role-specific "how-to" documents so that day-to-day users could operate confidently on the new system without dependency on the migration team. These guides covered report generation, filter logic, and common troubleshooting steps.

For more details see [LinkedIn](https://www.linkedin.com/in/pramodmisra/) | [GitHub](https://github.com/pramodmisra)
