---
layout: default
title: "CMS Overall Hospital Quality Star Rating Guidance"
---

# CMS Overall Hospital Quality Star Rating Guidance

## Authoritative versus demonstration values

The platform exposes three distinct concepts:

| Value | Meaning |
|---|---|
| Published Overall Star Rating | Authoritative rating published by CMS |
| Demo Calculated Star Score | AMC demonstration score derived from available CMS results |
| Demo Scenario Score | Illustrative improvement scenario |

The latter two are not reproductions or forecasts of an official CMS rating.
Reports and agents must use these labels explicitly.

## Current CMS methodology concepts

The April 2026 CMS methodology uses five groups:

| Group | Weight |
|---|---:|
| Mortality | 22% |
| Safety of Care | 22% |
| Readmission | 22% |
| Patient Experience | 22% |
| Timely and Effective Care | 12% |

At a high level, CMS:

1. Selects eligible measures for the rating release.
2. Standardizes measures and aligns directionality.
3. Calculates measure-group scores.
4. Redistributes weights when a hospital lacks an eligible group.
5. Combines group scores into a summary score.
6. Assigns hospitals to three-, four-, or five-group peer groups.
7. Uses clustering within peer groups to assign one through five stars.
8. Applies methodology-version-specific rules, including the 2026 Safety of
   Care restriction where applicable.

Always consult the methodology document associated with the specific rating
release. Do not assume that measure inclusion, periods, clustering boundaries,
or special rules remain constant.

## Platform limitation

The current `scorecard.fact_star_rating_scorecard` calculated score averages
available performance percentiles and maps them to a one-to-five scale. It
does not currently perform the complete CMS standardization, weighting,
peer-group, clustering, or safety-restriction process.

The shared model therefore treats:

- `published_overall_star_score` as authoritative.
- `calculated_overall_star_score` as a demo calculation.
- `scenario_score` as an illustrative scenario.

## Team rules

- Do not rename a demo score to “CMS Star Rating.”
- Do not imply that a half-point scenario produces an official rating change.
- Preserve measure directionality.
- Keep reporting periods and source releases visible.
- Avoid averaging unrelated measure units without standardization.
- Do not combine synthetic patient outcomes with real CMS facility results as
  if one caused the other.

## Future methodology replica

A defensible CMS methodology replica should materialize these items in Gold:

- Methodology version and effective release
- Included measures and reporting periods
- Eligibility and suppression rules
- Standardized measure values
- Group scores
- Available-group count and redistributed weights
- Summary score
- Peer-group assignment
- Cluster boundaries and assigned rating
- Safety restriction result
- Comparison with the published rating

Complex annual standardization and clustering should be calculated upstream,
not implemented only as interactive DAX.

## References

- [CMS Overall Hospital Quality Star Rating resources](https://qualitynet.cms.gov/inpatient/public-reporting/overall-ratings/resources)
- [CMS Provider Data Catalog: Overall hospital quality star rating](https://data.cms.gov/provider-data/topics/hospitals/overall-hospital-quality-star-rating/)

**Next:** [07 Lab 2: Make a semantic model AI-ready](07_lab2_ai_ready_model.html)
