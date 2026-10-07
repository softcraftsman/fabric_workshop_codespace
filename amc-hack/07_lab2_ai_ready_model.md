---
layout: default
title: "Lab 2: Make a Semantic Model AI-Ready"
---

# Lab 2: Make a Semantic Model AI-Ready

**Goal:** Build a small semantic model and prepare it so Copilot and Data
Agents give accurate, well-explained answers.

**Time:** 40–45 minutes.

**You will build:** A team-owned Direct Lake model for the Readmissions slice.
Labs 3 and 4 use it.

**You need:** The baseline numbers from Lab 1.

This lab follows the **advanced path** from page 10, scoped to one fact table
so everyone gets comparable results. The shared model, **AMC Shared
Foundation**, remains the governed reference.

## Why this matters

AI tools answer from the names, descriptions, and relationships in your model.
A model with cryptic column names and no descriptions produces confident but
wrong answers. Preparing the model is the single most effective way to improve
AI results.

## Part A: Create the model

1. In your team workspace, create a new semantic model from `GoldLakehouse`.
2. Select these tables:
   - `quality.fact_readmission`
   - `conformed.dim_facility`
   - `conformed.dim_date`
   - `conformed.dim_diagnosis`
3. Name the model `Readmissions Model`.

## Part B: Relationships

Open the model view and confirm or create these many-to-one relationships from
the fact to each dimension. Keep them single-direction.

| From (fact) | To (dimension) |
|---|---|
| `fact_readmission[facility_key]` | `dim_facility[facility_key]` |
| `fact_readmission[date_key]` | `dim_date[date_key]` |
| `fact_readmission[diagnosis_key]` | `dim_diagnosis[diagnosis_key]` |

## Part C: Add measures

Add these measures to `fact_readmission`. Use Copilot to draft the
descriptions, then edit them for accuracy.

```dax
Eligible Discharges = COUNTROWS(fact_readmission)

30-Day Readmissions =
COALESCE(
    CALCULATE(COUNTROWS(fact_readmission),
              fact_readmission[readmitted_30_days_flag] = TRUE()),
    0)

30-Day Readmission Rate =
DIVIDE([30-Day Readmissions], [Eligible Discharges])
```

Set the rate's format to percentage with one decimal place.

> **Why COALESCE**
>
> A facility with zero readmissions would otherwise show a blank rate and
> vanish from ranked lists, while poor performers stayed visible. The
> COALESCE keeps perfect performers in view.

## Part D: Reconcile with Lab 1

Create a quick table visual or use DAX query view to evaluate
`Eligible Discharges` and `30-Day Readmission Rate` with no filters.

Compare them with your Lab 1 numbers. **They must match.** If they do not,
check the relationships before continuing.

## Part E: Describe and tidy

1. Hide technical columns: all `*_key` columns and flag columns that are
   already covered by a measure.
2. Add a **description** to every table, to each visible column, and to each
   measure. A good description says what it means, the grain, and the units.
3. State the provenance in the fact table description: *synthetic patient-level
   events, not real hospital outcomes*.

## Part F: Prepare the model for AI

1. Open **Prepare data for AI** on the model.
2. **AI data schema:** Select only the tables, columns, and measures people
   should ask about. Leave out technical columns.
3. **AI instructions:** Add short, specific guidance, for example:

   > Readmission data is synthetic. Always show the 30-Day Readmission Rate as
   > a percentage. When asked about "performance," use the 30-Day Readmission
   > Rate. Do not call any value an official CMS rating.

4. **Verified answers:** Add two or three example questions with approved
   visuals, such as "Which facilities have the highest 30-day readmission
   rate?"
5. Optionally, add synonyms to key columns (for example "hospital" for
   `facility_name`).

## Part G: Test it

Ask Copilot three questions about the model. Note which answers are correct,
which are vague, and which description or instruction would fix them. Update
the model and ask again.

## Expected result

A published `Readmissions Model` whose numbers match Lab 1, with descriptions,
AI instructions, and at least two verified answers.

## If you get stuck

- **Numbers do not match Lab 1:** Check relationships, then check whether a
  filter is applied.
- **Direct Lake errors:** Confirm you have read access to the Gold tables.
- **Still stuck:** Use the checkpoint model from your facilitator, then
  continue with Lab 3.

**Next:** [08 Lab 3: Build a report](08_lab3_report.html)
