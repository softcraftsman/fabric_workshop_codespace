---
layout: default
title: "Lab 1: Explore the Data with Copilot in a Notebook"
---

# Lab 1: Explore the Data with Copilot in a Notebook

**Goal:** Learn what is in the Gold tables by asking Copilot questions, and
verify its answers yourself.

**Time:** 30–40 minutes.

**You will build:** A notebook that profiles the Readmissions data. Later labs
reuse the numbers you record here.

**You need:** A notebook in your team workspace (from the environment check).

> **About the screens**
>
> Fabric changes often. Button names may differ slightly from these
> instructions. If you cannot find something, ask Copilot or your facilitator.

## Part A: Attach the data

1. Open your new notebook and name it `Lab 1 - Explore Readmissions`.
2. In the Explorer pane, choose **Add data items** and add the existing
   `GoldLakehouse` from the **AMC Data Engineering** workspace.
3. Expand `GoldLakehouse` and note the schemas: `conformed`, `quality`,
   `benchmark`, and `scorecard`.

## Part B: Ask Copilot what is there

1. Open the **Copilot** pane from the ribbon.
2. Ask:

   > List the tables in the conformed and quality schemas of GoldLakehouse
   > with their row counts.

3. Insert the generated code into a cell and run it.
4. Compare the result with the Explorer pane. They should match.

> **Why verify**
>
> Copilot writes plausible code. Running it and checking the result is how
> you build trust. Always look at the code before you run it.

## Part C: Understand the Readmissions fact

The table `quality.fact_readmission` has **one row per eligible index
discharge**. Ask Copilot:

> Show the columns and data types of quality.fact_readmission and explain what
> each column likely means.

Then ask:

> Join quality.fact_readmission to conformed.dim_facility on facility_key and
> show the 30-day readmission rate for each facility. The rate is the share of
> rows where readmitted_30_days_flag is true.

Run the code. Confirm that facilities appear once each and that the rate falls
between 0% and 100%.

## Part D: Look at distributions

Ask Copilot for each of these, and run them:

1. The number of eligible discharges per `calendar_year`, joining to
   `conformed.dim_date` on `date_key`.
2. The top 10 diagnoses by discharge count, joining to
   `conformed.dim_diagnosis` on `diagnosis_key` and using `description`.
3. The average `length_of_stay` for readmitted versus non-readmitted
   discharges.

## Part E: Try Data Wrangler

1. Load `quality.fact_readmission` into a DataFrame.
2. On the **Data** tab, open **Data Wrangler** for that DataFrame.
3. Review the column profiles, then find any columns with missing values.

## Part F: Separate synthetic from real

Open `benchmark` and `scorecard` in the Explorer. Write down, in a markdown
cell, one sentence answering each:

- Which tables in this lab hold **synthetic** patient-level events?
- Which tables hold **authoritative CMS** facility-level results?

Page 06 explains why this distinction matters.

## Record your numbers

In a markdown cell, record these values. Lab 2 will check your model against
them.

| Item | Your value |
|---|---|
| Rows in `quality.fact_readmission` | |
| Distinct facilities with discharges | |
| Overall 30-day readmission rate | |

## Expected result

You can describe the Readmissions fact, you have a notebook with working
queries, and you have recorded baseline numbers.

## If you get stuck

- **Copilot returns code that fails:** Paste the error message back into
  Copilot and ask it to fix the code.
- **Schema not found:** Confirm that `GoldLakehouse` is attached and use
  `schema.table` names such as `quality.fact_readmission`.
- **Still stuck:** Open the checkpoint notebook from your facilitator.

**Next:** [05 Shared platform](05_shared_platform.html)
