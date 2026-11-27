# CivicSphere NG — Model Safety Statement

**Owner:** Models Team — Innocent Ojisua  
**Documentation date:** 27 November 2026  
**Applies to:** Claim Desk, Result Checker, Voter Assistant and Climate Access

## 1. Overall safety position

CivicSphere's intelligence modules are decision-support prototypes built using synthetic project datasets.

Their outputs are intended to support information retrieval, screening, prioritisation and human review. They must not independently determine election legitimacy, voter eligibility, electoral malpractice or the safety of a polling location.

## 2. Synthetic-data limitation

The datasets supplied for development are synthetic and fictional. They are not evidence of actual election events, polling-unit conditions or voter behaviour.

Model performance on these datasets must not be represented as demonstrated performance in a real election.

## 3. Human oversight

Human review is required before consequential decisions are made using model outputs.

In particular:

- Claim Desk classifications must not be published as confirmed fact-check verdicts without evidence review.
- Result Checker anomaly flags must not be treated as proof of fraud or manipulation.
- Voter Assistant responses must rely on approved and current information sources.
- Climate Access advisories must be checked against actual local conditions before operational decisions.

## 4. Uncertainty and errors

All four modules can produce incorrect, incomplete or misleading outputs.

Confidence scores, similarity scores, anomaly flags and heuristic risk scores have different meanings. They must not be presented interchangeably as probabilities or guarantees.

The Result Checker may generate false positives. The Claim Desk may misclassify unfamiliar claims. The Voter Assistant may retrieve an irrelevant FAQ. Climate Access may overstate or understate accessibility risk because of its configured weights and incomplete information.

## 5. Privacy and data minimisation

The model layer should process only the information required for its intended function.

It must not request voter identification numbers or unnecessary personal information. Reporter identity should not be introduced into model inputs by default.

The shared backend and privacy gate remain responsible for enforcing the architecture's access, retention, aggregation and deletion requirements.

## 6. Language and inclusion

English and available Pidgin drafts are the current working language targets.

Hausa, Yoruba and Igbo performance has not been established. The system must not claim reliable support for languages that have not been adequately populated, reviewed and evaluated.

## 7. Source integrity

The Voter Assistant must distinguish approved sources from synthetic or unverified material.

A retrieved FAQ reference is not automatically an official source citation. Public-facing answers should use approved, traceable and current source documents.

## 8. Appropriate use

Permitted prototype uses include:
- Internal demonstrations using synthetic data.
- Model evaluation and development.
- Preliminary screening and review prioritisation.
- Testing integration with the CivicSphere backend.

Not permitted:
- Automated declarations that an election is fraudulent or compromised.
- Public accusations based solely on anomaly scores.
- Fabricated or unsupported election guidance.
- Claims of weather forecasting from accessibility-only data.
- Claims of real-world accuracy based solely on synthetic evaluation.

## 9. Deployment conditions

Before production or public election use, the team should:
- Connect approved and maintained source material.
- Evaluate against representative, independently reviewed data.
- Review thresholds and false-positive behaviour.
- Test supported languages with competent speakers.
- Provide human-review and correction mechanisms.
- Ensure backend privacy and security controls are active.
- Document model versions, dependencies and changes.

## 10. Final statement

CivicSphere's intelligence layer is designed to assist people, not replace accountable human judgement. Its outputs should be interpreted as indicators requiring context, evidence and appropriate review.
