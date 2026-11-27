# Claim Desk — Model Card

**Project:** CivicSphere NG  
**Module:** Claim Desk  
**Owner:** Models Team — Innocent Ojisua  
**Documentation date:** 27 November 2026  
**Status:** Prototype — synthetic-data evaluation

## 1. Purpose

Claim Desk supports the identification and prioritisation of potentially misleading election-related claims. It classifies submitted text, retrieves similar claims from the available dataset and calculates a preliminary risk score.

It is a decision-support tool. It does not independently establish the truth or falsity of a claim.

## 2. Intended use

- Classify election-related claims into available categories.
- Retrieve similar previously recorded claims.
- Prioritise claims for human fact-checking.
- Provide structured outputs for the shared CivicSphere backend.

## 3. Model and methodology

The classification component uses a TF-IDF text representation with unigrams and bigrams, followed by Logistic Regression with balanced class weights.

Similar-claim retrieval uses TF-IDF vectors and cosine similarity.

The preliminary risk score combines:
- Claim spread score, scaled to a maximum contribution of 70.
- Synthetic media indicator, contributing up to 30 points.

The resulting score is a prioritisation heuristic, not a probability of misinformation.

## 4. Dataset

The model uses the project's synthetic misinformation claims dataset.

- Total records: 300.
- Training records: 240.
- Held-out test records: 60.
- Available labels: false, misleading, true and unverifiable.

The dataset contains fictional, template-generated examples. It is not a representative sample of real election misinformation.

## 5. Evaluation

Held-out test accuracy: **100%**.

The classification report showed precision, recall and F1-score of 1.00 for each of the four classes on the 60-record test split.

This result applies only to the supplied synthetic dataset. Template similarity and repeated text patterns may make the task substantially easier than real-world misinformation classification.

## 6. Limitations

- No independent real-world election claim evaluation has been completed.
- Similarity does not establish factual correctness.
- No approved external fact-check corpus is currently integrated into this prototype.
- Risk scoring depends on supplied spread and media indicators.
- Model confidence is not a guarantee of correctness.
- Language performance outside the evaluated dataset is unknown.

## 7. Human oversight

Claims flagged by the system should be reviewed against credible evidence by authorised human fact-checkers before a public verdict is issued.

## 8. Deployment recommendation

Use as a preliminary screening and prioritisation component. Do not publish automated classifications as confirmed fact-check decisions.
