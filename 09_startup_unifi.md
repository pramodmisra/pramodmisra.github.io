---
layout: page
title: Unifi.ai — Data Privacy Platform
permalink: /09_startup_unifi
---
## Unifi.ai — Data Privacy Platform for Healthcare

<img src="images/09_startup_unifi.jpg?raw=true"/>

---

Co-founded Unifi.ai and served as Chief AI Officer at this Atlanta-based health-tech startup. The platform was built to solve a critical gap in enterprise data privacy: most organizations invest heavily in perimeter security but neglect the encryption and compliance controls around employee document sharing and data access. Unifi.ai uses machine learning to automate PII detection, one-click encryption, and privacy impact assessments — reducing setup time to one-third of the traditional process. The company was selected into the Georgia Tech CreateX program, Google Cloud Startup Program, and Microsoft for Startups, and received coverage in Forbes, Entrepreneur, Inc., and NY Weekly.

**1. Build an ML-powered PII detection and encryption engine**

Developed NLP-based machine learning models that identify personally identifiable information (names, SSNs, credit card numbers, etc.) across documents in real time. When PII is detected, the system highlights it for the admin and offers one-click encryption using SHA-256 — the industry gold standard — without requiring the end user to be a privacy expert.

```python
# Example: PII detection pipeline skeleton
import re
from typing import List

PII_PATTERNS = {
    "ssn": r"\b\d{3}-\d{2}-\d{4}\b",
    "credit_card": r"\b\d{4}[-\s]?\d{4}[-\s]?\d{4}[-\s]?\d{4}\b",
    "email": r"[a-zA-Z0-9_.+-]+@[a-zA-Z0-9-]+\.[a-zA-Z0-9-.]+",
}

def detect_pii(text: str) -> List[dict]:
    findings = []
    for pii_type, pattern in PII_PATTERNS.items():
        matches = re.finditer(pattern, text)
        for m in matches:
            findings.append({"type": pii_type, "value": m.group(), "start": m.start(), "end": m.end()})
    return findings
```

**2. Automate privacy impact assessments (PIA)**

Tackled one of the biggest bottlenecks in compliance: the Privacy Impact Assessment process. Used ML to map NIST/ISO27001 framework questions to the right departments automatically, reducing the time spent on questionnaire routing and completion. Built an in-house tool with pre-built ML libraries that let users visualize data flow diagrams in hours rather than weeks.

**3. Enable multi-regulation compliance with a single platform**

Unifi.ai handles GDPR, CCPA, HIPAA, and other frameworks simultaneously. The platform generates standard contractual clauses, risk matrices, and compliance reports — all automatically — so companies don't need to hire separate privacy consultants for each regulation.

```python
# Example: Multi-regulation compliance checker
REGULATIONS = {
    "GDPR": {"requires_consent": True, "right_to_erasure": True, "dpia_required": True},
    "CCPA": {"requires_consent": False, "opt_out_right": True, "dpia_required": False},
    "HIPAA": {"requires_baa": True, "encryption_required": True, "dpia_required": True},
}

def check_compliance(org_config: dict) -> dict:
    results = {}
    for reg, rules in REGULATIONS.items():
        gaps = [rule for rule, required in rules.items() if required and not org_config.get(rule)]
        results[reg] = {"status": "compliant" if not gaps else "gaps_found", "gaps": gaps}
    return results
```

**4. Publish research and gain industry recognition**

Co-authored a scholarly paper on the impact of machine learning techniques in privacy compliance. Contributed an opinion piece to IAPP (International Association of Privacy Professionals) on how ML can help small businesses navigate data privacy. Recognized as a Young Privacy Professional leader by IAPP.

For more details see [Entrepreneur](https://www.entrepreneur.com/en-in/technology/this-platform-is-grammarly-for-data-privacy/441441) | [NY Weekly](https://nyweekly.com/tech/unifi-ai-brings-flexible-automated-solutions-to-data-privacy-compliance/) | [IAPP](https://iapp.org/news/a/how-machine-learning-can-help-small-businesses-deal-with-data-privacy-compliance/) | [Scholarly Paper](https://turcomat.org/index.php/turkbilmat/article/view/13130) | [LinkedIn](https://www.linkedin.com/in/pramodmisra/) | [GitHub](https://github.com/pramodmisra)
