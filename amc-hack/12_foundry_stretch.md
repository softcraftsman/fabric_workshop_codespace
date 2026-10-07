---
layout: default
title: "Foundry and Agent Stretch Work"
---

# Foundry and Agent Stretch Work

This page is optional. Use it when your team has a working report and Data
Agent and wants to go further.

## Shared Foundry project

The organizers provide **one shared Foundry project** with a deployed model.
You do not create Azure resources. Your facilitator will give you:

- The project endpoint
- The model deployment name
- Instructions for signing in with your workshop account

Use it for ideas such as:

| Team domain | Example use |
|---|---|
| Patient Experience | Summarize or tag themes in synthetic survey comments from a notebook |
| Preventive Care | Draft outreach messages for a care-gap cohort |
| Safety | Summarize a cluster of safety events for an investigation note |
| Any team | Ask the model to explain a metric definition in plain language |

> **Keep it safe**
>
> Send only synthetic data and metric definitions to the model. Never send
> credentials or real patient data. Do not describe model output as an
> official CMS result.

## Call a Data Agent from a Foundry agent

Your facilitator has built a sample **Foundry agent** that calls Fabric Data
Agents. It shows the pattern for combining several domain agents behind one
conversation.

1. Open the sample agent in the shared Foundry project and read its
   instructions.
2. Ask it a question that needs one of the Data Agents, for example "What is the
   30-day readmission rate?"
3. Read the tool or connection configuration to see how it reaches the Data
   Agent.
4. Register **your** team's Data Agent as an additional tool, then ask a
   question only your agent can answer.

## What to show in your demo

If you extend your solution, add one of these to your demo:

- A notebook cell that calls the shared model to produce something useful
- Your Data Agent reachable from the sample Foundry agent

## If you get stuck

- Ask your facilitator for access if the project or model is not visible.
- If you cannot connect your Data Agent, demo it directly in Fabric instead.
