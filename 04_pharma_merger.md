---
layout: page
title: Post-Merger Data Standardization
permalink: /04_pharma_merger
---
## Post-Merger Data Standardization — Fortune 500 Pharma, Boston

<img src="images/04_pharma_merger.jpg?raw=true"/>

---

Led data standardization for a Fortune 500 pharmaceutical company in Boston following its merger with a leading biotech firm. The merger had left behind deeply conflicting terminology, business definitions, and incomplete documentation across both entities. The goal was to produce a unified, clean data catalogue and dictionary that could support a reliable database migration going forward.

**1. Build the data catalogue and data dictionary**

Worked with business, technology, and vendor teams to construct a comprehensive data catalogue. The dictionary was built incrementally — starting with the most critical entities and expanding outward — ensuring buy-in at every stage.

```python
# Example: Conflict-detection between two merged schemas
import pandas as pd

def detect_conflicts(schema_a: pd.DataFrame, schema_b: pd.DataFrame, key="field_name"):
    merged = schema_a.merge(schema_b, on=key, how="inner", suffixes=("_a", "_b"))
    conflicts = merged[merged["definition_a"] != merged["definition_b"]]
    return conflicts[[key, "definition_a", "definition_b"]]
```

**2. Present high-level data flow diagrams for confirmation**

Before diving into granular mapping, produced a high-level data flow diagram covering all major systems and handoff points. This was reviewed and signed off by senior stakeholders to lock in the architectural direction.

**3. Apply incremental agile approach — one business unit at a time**

Rather than a big-bang rollout, adopted an incremental strategy: standardize one business unit and one report at a time, validate, then move to the next. Each iteration proposed an improved solution that linked back to the master structure agreed upon in the earlier phases.

```python
# Example: Incremental validation tracker
def track_unit_status(units: list) -> pd.DataFrame:
    return pd.DataFrame(units, columns=[
        "business_unit", "fields_total", "fields_standardized",
        "reports_migrated", "status"  # status: pending | in_progress | validated
    ])
```

**4. Resolve legacy documentation gaps**

Identified and filled documentation gaps inherited from the biotech merger. Created clear field-level descriptions, business rules, and owner assignments so the downstream migration team had a single authoritative reference.

For more details see [LinkedIn](https://www.linkedin.com/in/pramodmisra/) | [GitHub](https://github.com/pramodmisra)
