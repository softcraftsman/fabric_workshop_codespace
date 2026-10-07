---
layout: default
title: "Lab 4: Build a Data Agent"
---

# Lab 4: Build a Data Agent

**Goal:** Create a Data Agent that answers natural-language questions about
readmissions, and measure how much your Lab 2 preparation helps.

**Time:** 40–45 minutes.

**You will build:** A `Readmissions Agent` that uses your semantic model.

**You need:** `Readmissions Model` from Lab 2.

## Part A: Create the agent

1. In your team workspace, create a new **Data Agent** named
   `Readmissions Agent`.
2. Add `Readmissions Model` as a data source.
3. Select the tables and measures the agent should be able to use. Leave out
   technical columns.

## Part B: Write instructions

Open the agent instructions and add guidance. Keep it short and specific:

> You answer questions about synthetic hospital readmission data.
> Always say that patient-level data is synthetic.
> Report the 30-Day Readmission Rate as a percentage.
> If a question cannot be answered from the model, say so instead of guessing.
> Never describe any value as an official CMS rating.

## Part C: Test with sample questions

Ask each of these and note whether the answer is correct, partially correct, or
wrong. Compare the numbers with your report.

1. How many eligible discharges are there?
2. What is the overall 30-day readmission rate?
3. Which five facilities have the highest 30-day readmission rate?
4. How did the readmission rate change by calendar year?
5. Which diagnosis categories have the most discharges?
6. Are these real hospital outcomes? *(The agent should say the data is
   synthetic.)*

## Part D: Improve it

For each wrong or weak answer, decide which fix applies:

| Problem | Fix |
|---|---|
| Wrong column used | Improve the description or add a synonym in the model |
| Wrong calculation | Add or correct a measure |
| Inconsistent wording or format | Tighten the agent instructions |
| Off-topic or unsafe answer | Add a limit to the instructions |

Make one change, retest, and record whether the answer improved.

## Part E: Add example questions

Add two or three example questions with approved answers so the agent behaves
consistently on common requests.

## Part F: Compare with and without preparation

If time permits, create a second agent that uses the same model but with
no instructions and no examples. Ask both agents the same three questions and
compare. This shows what each layer of preparation contributes.

## Expected result

A working Data Agent whose answers on the sample questions match your report,
and a list of the changes that improved it.

## If you get stuck

- **Agent cannot see the model:** Confirm the model is published and that you
  selected its tables.
- **Answers disagree with the report:** Check the measure definitions in the
  model.
- **Still stuck:** Use the checkpoint agent from your facilitator.

## What you can now do

You have explored data with Copilot, prepared a model for AI, built a report,
and built a Data Agent. These are the building blocks for the open hack.

**Next:** [10 Open hack kickoff](10_open_hack_kickoff.html)
