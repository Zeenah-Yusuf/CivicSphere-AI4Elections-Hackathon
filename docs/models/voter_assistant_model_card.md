# Voter Assistant — Model Card

**Project:** CivicSphere NG  
**Module:** Voter Assistant  
**Owner:** Models Team — Innocent Ojisua  
**Documentation date:** 27 November 2026  
**Status:** Prototype — synthetic FAQ retrieval

## 1. Purpose

Voter Assistant retrieves relevant election-information answers from an available FAQ knowledge base. It returns a source reference and abstains when the retrieved content does not meet a configured similarity threshold.

## 2. Intended use

- Retrieve relevant voter-information FAQs.
- Return answers associated with the selected FAQ record.
- Identify the source FAQ ID and topic.
- Abstain when available information is insufficiently relevant.
- Support integration with the approved CivicSphere information corpus.

## 3. Methodology

The prototype uses TF-IDF vectorisation with unigrams and bigrams.

Cosine similarity ranks the FAQ records against a submitted question. The highest-scoring record is returned when its similarity meets the configured threshold of 0.12 and a non-empty answer is available.

The prototype returns the FAQ ID and topic as source references.

## 4. Dataset

The supplied FAQ dataset contains 20 records.

English and available Pidgin draft text are used for retrieval. Hausa, Yoruba and Igbo fields are incomplete or empty in the supplied dataset.

The Pidgin drafts have not been established as independently reviewed translations.

## 5. Evaluation

The retrieval index was successfully built over all 20 FAQ records.

A formal, independently labelled retrieval evaluation has not yet been completed. The similarity threshold is a prototype configuration and should be calibrated against representative voter questions.

## 6. Limitations

- The current FAQ corpus is synthetic and limited in size.
- Source references identify FAQ records, not independently verified official publications.
- TF-IDF similarity measures textual relevance, not factual correctness.
- The system may retrieve an incorrect or incomplete answer.
- Unsupported questions may not always be recognised by the threshold.
- Multilingual performance has not been established for Hausa, Yoruba or Igbo.

## 7. Human oversight

Election information intended for public use must come from approved and current sources. Content should be reviewed for accuracy, language quality and relevance. The system should abstain rather than invent an answer when reliable information is unavailable.

## 8. Deployment recommendation

Use as a retrieval prototype. Connect it to the approved, reviewed and maintained `corpus_docs` knowledge base before presenting responses as authoritative election guidance.
