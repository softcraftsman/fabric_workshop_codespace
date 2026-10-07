---
layout: default
title: "Open Hack Kickoff"
---

# Open Hack Kickoff

You have completed the four guided labs. Now you apply them. Each team picks
one healthcare-quality challenge (page 11) and builds its own solution. Use the
labs as your reference:

| Skill | Where you learned it |
|---|---|
| Explore data with Copilot | [Lab 1](04_lab1_notebook_ai.html) |
| Prepare a semantic model for AI | [Lab 2](07_lab2_ai_ready_model.html) |
| Build a report | [Lab 3](08_lab3_report.html) |
| Build a Data Agent | [Lab 4](09_lab4_data_agent.html) |

## Workspace preparation

Each team receives its own Fabric-capacity workspace with:

- Contributor access for team members
- Git integration to a team-specific repository folder or branch
- Build permission on the shared semantic models
- Read access to the required Gold tables
- Permission to create notebooks, semantic models, reports, ontologies, agents,
  event-driven items, and experiments

Recommended workspace names:

- `AMC Readmissions`
- `AMC Mortality`
- `AMC Patient Experience`
- `AMC Safety`
- `AMC Preventive Care`
- `AMC Access and Effectiveness`

## Two supported starting paths

### Starter path

Connect a thin Power BI report or Data Agent to **AMC Shared
Foundation**. This path is appropriate when the team wants to focus on report,
agent, or Fabric IQ skills without rebuilding the model.

### Advanced path

Create a team-owned Direct Lake semantic model over the assigned Gold fact and
the shared dimensions. This path is appropriate when semantic-model design is
part of the team's learning objective.

The advanced model must preserve the shared table grains, keys, provenance,
and CMS definitions.

## Suggested open-hack sequence

1. Inspect the assigned fact table and its grain (as in Lab 1).
2. Connect to the shared semantic model or create a domain model (as in Lab 2).
3. Reconcile baseline counts with the shared model.
4. Define the team's primary question and success metric.
5. Build one trustworthy analytical view before adding AI.
6. Add a Fabric item that demonstrates a new capability.
7. Document assumptions and provenance.
8. Prepare a repeatable demo path.

## Required team metadata

Every published measure should include:

| Field | Requirement |
|---|---|
| Name | Unique, business-readable name |
| Description | What the measure means |
| Grain | Level at which it is valid |
| Numerator | Included records or values |
| Denominator | Eligible population |
| Exclusions | Explicit exclusions |
| Directionality | Higher, lower, or target is better |
| Provenance | CMS, Synthea, synthetic supplemental, or derived |
| Owner | Responsible team |
| Status | Experimental, reviewed, or approved |

## Validation checklist

- Fact counts reconcile with the assigned Gold table.
- Dimension filters do not unexpectedly remove fact rows.
- Rates use explicit numerators and denominators.
- Measures do not sum percentages or ratings.
- Reporting-period filters are visible.
- CMS values use the exact labels **Published Overall Star Rating**, **Demo
  Calculated Star Score**, and **Demo Scenario Score**, and are visually
  distinct.
- Synthetic events are labeled.
- Reports and agents do not imply that synthetic patient events caused real
  CMS facility performance.
- Patient or provider attributes are used appropriately.
- Provider analysis is not presented as individual performance evaluation.
- The demo works from a clean browser session.
- Source changes are committed to Git.

## Demo checklist

Each team should be able to explain:

1. The healthcare-quality problem it selected.
2. The Fabric items it created.
3. The data and measures used.
4. The insight or decision enabled.
5. How provenance and limitations are communicated.
6. What you would build next with more time.

**Next:** [11 Open hack challenges](11_open_hack_challenges.html)
