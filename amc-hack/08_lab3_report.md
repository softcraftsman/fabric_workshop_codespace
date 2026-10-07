---
layout: default
title: "Lab 3: Build a Report with Copilot"
---

# Lab 3: Build a Report with Copilot

**Goal:** Turn your semantic model into a clear report page, and see how the
preparation in Lab 2 improves Copilot's output.

**Time:** 30–40 minutes.

**You will build:** A one-page Readmissions report.

**You need:** `Readmissions Model` from Lab 2, and a review of the labeling
rules on page 06.

## Part A: Create the report

1. In your team workspace, open `Readmissions Model` and choose **Create a
   report** (or create a new report and connect it to the model).
2. Name the report `Readmissions Overview`.

## Part B: Generate a page with Copilot

1. Open the **Copilot** pane in the report.
2. Ask:

   > Create a page that shows the 30-Day Readmission Rate by facility, the
   > trend over time by calendar year, and the top diagnoses by eligible
   > discharges.

3. Review what Copilot created. Check each visual against what you expect from
   Lab 1.

## Part C: Refine

Use prompts or the formatting pane to make these changes:

1. Add a card for **Eligible Discharges** and one for **30-Day Readmission
   Rate**.
2. Sort the facility chart so the highest rate appears first.
3. Add a slicer for `calendar_year` and one for `condition_category`.
4. Give every visual a plain-language title.

Ask Copilot to suggest a one-sentence summary of the page, then edit it so it is
accurate.

## Part D: Label it correctly

Add a visible text box:

> Patient-level readmission events in this report are **synthetic** and do not
> represent real hospital outcomes.

Do not use the words "CMS Star Rating" anywhere in this report. If you later
show CMS values, use the exact labels **Published Overall Star Rating**, **Demo
Calculated Star Score**, and **Demo Scenario Score**.

## Part E: See the effect of preparation

Ask Copilot the same question twice:

1. Once with the wording from Lab 2's descriptions.
2. Once using vague wording, such as "Which hospitals are doing badly?"

Notice how well the measure names and instructions guide the answer.

## Part F: Validate

- [ ] Totals match Lab 1 and Lab 2.
- [ ] Rates are shown as percentages, not summed.
- [ ] The reporting period filter is visible.
- [ ] The synthetic-data label is visible.
- [ ] The report opens correctly in a private browser window.

## Expected result

A published report that matches your earlier numbers and carries the right
labels.

## If you get stuck

- **Copilot builds the wrong visual:** Rephrase with the exact measure and
  column names.
- **Visuals are blank:** Check that the report is connected to your model and
  that you are not filtering everything out.
- **Still stuck:** Open the checkpoint report from your facilitator.

**Next:** [09 Lab 4: Build a Data Agent](09_lab4_data_agent.html)
