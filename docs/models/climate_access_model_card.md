# Climate Access — Model Card

**Project:** CivicSphere NG  
**Module:** Climate Access  
**Owner:** Models Team — Innocent Ojisua  
**Documentation date:** 27 November 2026  
**Status:** Prototype — rule-based accessibility advisory

## 1. Purpose

Climate Access currently assesses polling-unit accessibility and operational-readiness indicators and generates practical advisories.

Despite the module's architecture name, the available prototype does not forecast weather or measure rainfall, heat or other meteorological conditions.

## 2. Intended use

- Identify polling units with accessibility and infrastructure concerns.
- Prioritise locations for operational support.
- Generate recommendations based on observed dataset indicators.
- Provide advisory information to the shared CivicSphere backend.

## 3. Methodology

The prototype uses transparent, rule-based scoring.

Its risk components include:
- Venue accessibility: maximum 35 points.
- Grid power availability: maximum 15 points.
- Network coverage: maximum 15 points.
- Distance to LGA headquarters: maximum 15 points.
- Information-access confidence from survey responses: maximum 20 points.

The combined score is capped at 100 and grouped into low, moderate, high and critical categories.

Advisories are generated from the corresponding observed indicators.

## 4. Dataset

The prototype combines:
- 900 polling-unit records.
- 500 accessibility survey records.

Survey information is aggregated by state and settlement before being joined to polling-unit records.

The project data is synthetic and does not establish the actual condition of real polling units.

## 5. Evaluation

The prototype generated accessibility assessments for 900 polling units.

| Risk category | Records |
|---|---:|
| Low | 46 |
| Moderate | 173 |
| High | 355 |
| Critical | 326 |

A total of 681 records were classified as high or critical.

These are descriptive outputs from the configured scoring rules, not independently validated predictions of accessibility failure.

## 6. Limitations

- The underlying data is synthetic.
- Risk weights and thresholds are heuristic.
- No independent outcome-based validation has been completed.
- Missing survey responses may affect information-access scoring.
- The dataset contains no rainfall, temperature, flooding or heat measurements.
- The current system cannot forecast weather-related risks.

## 7. Human oversight

Advisories should be treated as prompts for further assessment and operational planning. Relevant authorities should verify conditions before taking action or publishing claims about a location.

## 8. Deployment recommendation

Present the current capability as polling-unit accessibility and operational-readiness advisory. Weather and climate forecasting must not be claimed without appropriate climate observations and a separately validated forecasting method.
