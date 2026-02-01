---
layout: page
title: AWS Redshift Migration & Cost Optimization
permalink: /03_pharma_redshift
---
## AWS Redshift Migration & Cost Optimization — North America Pharma Company

<img src="images/03_pharma_redshift.jpg?raw=true"/>

---

Migrated the entire data infrastructure — feeds, reports, and dashboards — from an on-premise data warehouse to AWS Redshift for one of the leading pharmaceutical companies in North America. The project required independently developing new SQL pipelines, rebuilding dashboards, and delivering tight quality-control loops — all while coordinating with business users, cross-functional teams, and external vendors. The engagement delivered approximately $1.5M in operational savings.

**1. Develop new SQL pipelines for feed generation and QC**

Designed and built SQL queries from scratch to replicate and improve upon legacy feed generation logic. Each query was paired with a corresponding quality-control check to catch schema drift, null rates, and row-count discrepancies before downstream consumption.

```sql
-- Example: Feed generation with built-in QC gate
WITH feed_raw AS (
    SELECT
        patient_id,
        drug_id,
        prescribed_date,
        dosage_mg
    FROM staging.prescriptions
    WHERE prescribed_date >= CURRENT_DATE - INTERVAL '90 days'
),
qc_check AS (
    SELECT
        COUNT(*) AS total_rows,
        COUNT(patient_id) AS non_null_patients,
        COUNT(DISTINCT drug_id) AS unique_drugs
    FROM feed_raw
)
SELECT * FROM feed_raw
WHERE (SELECT total_rows FROM qc_check) > 0
  AND (SELECT non_null_patients FROM qc_check) = (SELECT total_rows FROM qc_check);
```

**2. Rebuild reports and dashboards on Redshift**

Translated every existing report and dashboard into the new Redshift-native environment. Worked directly with end users to validate outputs and incorporated feedback iteratively before sign-off.

**3. Coordinate UAT with stakeholders across teams**

Ran a structured user acceptance testing cycle with key stakeholders. Ensured all migrated reports matched expected outputs and documented any edge cases for post-migration monitoring.

**4. Deliver $1.5M in operational savings**

The streamlined cloud architecture eliminated redundant on-premise infrastructure costs and reduced query runtimes significantly. Active coordination across business, technology, and vendor teams was critical to realizing these savings on schedule.

For more details see [LinkedIn](https://www.linkedin.com/in/pramodmisra/) | [GitHub](https://github.com/pramodmisra)
