---
layout: default
title: "Open Hack Challenges"
---

# Open Hack Challenges

Teams own the analytical and experiential layer for their assigned domain.
The examples below are starting points, not required implementations.

Each challenge builds on the guided labs. The Readmissions team can start from
the lab results directly; other teams repeat the same steps on their own fact
table.

| Lab skill | Apply it to your domain by... |
|---|---|
| Lab 1: Explore | Profiling your primary fact table and its grain |
| Lab 2: AI-ready model | Building a model over your fact and the shared dimensions |
| Lab 3: Report | Building a report that answers your team's primary question |
| Lab 4: Data Agent | Building an agent for your domain's questions |

## Readmissions

Primary data: `quality.fact_readmission`

Potential questions:

- Which diagnoses, populations, and facilities drive readmissions?
- Where are post-discharge emergency visits increasing?
- Which cohorts have the greatest preventable-risk opportunity?

Suggested Fabric work:

- Domain semantic model and readmission measures
- Driver-analysis report
- Risk-cohort notebook or ML experiment
- Readmission data agent
- Intervention scenario or outreach workflow

## Mortality

Primary data: `quality.fact_mortality`

Potential questions:

- What drives observed-to-expected mortality?
- Which populations have elevated risk?
- How do sepsis and intensive-care indicators affect patterns?

Suggested Fabric work:

- Observed-to-expected model
- Risk-segmentation report
- Explainable predictive experiment
- Mortality ontology extension
- Clinical-quality agent

The `quality.fact_mortality.expected_mortality` value is produced by a
demonstration risk model and must not be described as a validated clinical
risk-adjustment methodology.

## Patient Experience

Primary data: `quality.fact_hcahps`

Potential questions:

- Which experience dimensions are declining?
- What differs by facility or service line?
- What themes are present in synthetic comments?

Suggested Fabric work:

- HCAHPS semantic extension
- Experience trend report
- Text-theme or sentiment notebook
- Patient-experience ontology
- Experience data agent

## Safety

Primary data: `quality.fact_patient_safety`

Potential questions:

- Which event types and harm levels are emerging?
- Where are HAI, fall, pressure-injury, or medication risks concentrated?
- Which signals should trigger additional investigation?

Suggested Fabric work:

- Safety-event model and report
- Anomaly-detection experiment
- Fabric Activator or event-driven demonstration
- Safety ontology extension
- Safety investigation agent

## Preventive Care

Primary data: `quality.fact_preventive_care`

Potential questions:

- Which populations have open care gaps?
- Which outreach cohorts should be prioritized?
- What factors are associated with lower completion?

Suggested Fabric work:

- Care-gap semantic model
- Outreach prioritization notebook
- Population-health report
- Preventive-care agent
- Intervention workflow

Preventive Care is a valuable enterprise domain but is not a separate group in
the CMS Overall Hospital Quality Star Rating. Applicable official measures
should be mapped to their CMS-designated group.

## Access and Effectiveness

Primary data: `quality.fact_access_effectiveness`

Potential questions:

- Which specialties or facilities have the longest waits?
- Where do referrals fail to convert?
- What contributes to no-shows and treatment delays?

Suggested Fabric work:

- Access semantic model
- Bottleneck report
- Scheduling or referral analysis notebook
- Operations or Data Agent
- Event-driven access alert

## Demo contract

Each team presents at the end of the day and should show:

- One report or user experience
- One reusable semantic or analytical artifact
- One concise set of reviewed findings
- One machine-consumable capability, such as an agent, ontology extension,
  notebook function, API, or MCP tool
- A list of assumptions, limitations, and provenance

Teams that finish early are encouraged to extend into the stretch work on
[page 12](12_foundry_stretch.html). Other teams should be able to understand
your metric definitions without reverse-engineering them.

Across every domain, teams must not imply that synthetic patient events caused
real CMS facility performance.

**Next:** [12 Foundry and agent stretch work](12_foundry_stretch.html)
