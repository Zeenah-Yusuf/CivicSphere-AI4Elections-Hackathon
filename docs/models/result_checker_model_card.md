# Result Checker — Model Card

**Project:** CivicSphere NG  
**Module:** Result Checker  
**Owner:** Models Team — Innocent Ojisua  
**Documentation date:** 27 November 2026  
**Status:** Prototype — synthetic-data evaluation

## 1. Purpose

Result Checker identifies numerical inconsistencies and unusual patterns in polling-unit election result records. It supports the prioritisation of records for human review.

An anomaly is not proof of electoral fraud or manipulation.

## 2. Intended use

- Check arithmetic and numerical consistency.
- Identify potentially suspicious result patterns.
- Detect unusual records using unsupervised anomaly detection.
- Produce risk scores and review indicators for the shared backend.

## 3. Methodology

The module combines transparent integrity rules with an Isolation Forest anomaly detector.

Rule checks include:
- Accredited voters exceeding registered voters.
- Ballot totals differing from accredited voters.
- Rejection rates exceeding the configured threshold.
- Suspicious round-number patterns.
- Duplicate vote-result patterns.

The unsupervised detector uses engineered features including turnout rate, rejected-vote rate, ballot difference rate, candidate vote shares, vote margin and vote concentration.

The combined prioritisation score adds rule-based risk points and an additional 20 points when the Isolation Forest identifies an anomaly, capped at 100.

## 4. Dataset

- Results records: 900.
- Held-out evaluation records: 180.
- Training records: 720.
- Evaluation labels: `anomaly_labels_HELD_OUT.csv`.

The held-out labels were not used to train the Isolation Forest.

## 5. Evaluation

Held-out evaluation results:

| Metric | Result |
|---|---:|
| Accuracy | 81% |
| Anomaly precision | 20% |
| Anomaly recall | 80% |
| Anomaly F1-score | 31% |

The anomaly class had 10 labelled examples in the held-out evaluation.

The results indicate that the detector identified a substantial proportion of labelled anomalies, but many alerts did not correspond to labelled anomalies.

## 6. Limitations

- Data and labels are synthetic.
- The anomaly detector may flag legitimate but unusual results.
- The rule thresholds are configurable heuristics, not legal standards.
- The combined risk score is not a fraud probability.
- The model does not establish intent, manipulation or responsibility.
- Performance on real election results has not been established.

## 7. Human oversight

Every flagged result requires examination by an authorised reviewer. Reviewers should consider source records, legitimate explanations, data-entry errors and relevant election procedures before making a decision.

## 8. Deployment recommendation

Use as a screening and review-prioritisation tool. Never treat an anomaly flag as an automatic finding of electoral malpractice.
