---
layout: default
title: "Shared Platform"
---

# Shared Platform

## Purpose

The shared platform removes setup friction and prevents incompatible
definitions without completing the domain work on behalf of participants.

## Shared data contract

All teams use the same conformed dimensions:

- Date
- Patient
- Organization
- Facility
- Provider
- Service Line
- Diagnosis
- Payer
- CMS Measure

The Gold facts preserve their documented grains:

| Fact | Grain |
|---|---|
| Readmission | One row per eligible index discharge |
| Mortality | One row per inpatient encounter |
| HCAHPS | One row per synthetic survey response |
| Patient Safety | One row per synthetic safety event |
| Preventive Care | One row per synthetic care opportunity |
| Access and Effectiveness | One row per synthetic scheduled service or referral |
| CMS Measure Result | One row per facility, measure, period, release, and source |
| CMS Benchmark | One row per measure, geography, period, and release |
| Star Rating Scorecard | One row per matched facility and source release |

## Shared semantic models

### Multi-AMC Shared Foundation

Shared responsibilities:

- Direct Lake access to managed Gold tables
- Fact-to-dimension relationships
- Hidden surrogate and technical columns
- Business-friendly descriptions and formatting
- Foundational counts, rates, and benchmark measures
- Explicit synthetic-data indicators
- Consistent CMS and reporting-period context

This model intentionally does not include domain-specific driver logic,
predictions, intervention scoring, or recommended actions.

### Multi-AMC CMS Stars Reference

Shared responsibilities:

- CMS measure catalog and directionality
- Facility-level CMS results
- National and North Carolina benchmark distributions
- CMS-published overall ratings
- The exact labels **Published Overall Star Rating**, **Demo Calculated Star
  Score**, and **Demo Scenario Score**
- Consistent facility and reporting-period context

These labels are mandatory in reports and agents. See
[CMS Stars guidance](06_cms_stars.html) for usage rules.

## Shared Fabric IQ vocabulary

The base ontology contains:

- Organization
- Facility
- Patient
- Provider
- Service Line
- CMS Measure
- Measure Result
- Benchmark
- Reporting Period
- Star Rating Assessment
- Readmission Event
- Mortality Encounter
- Experience Survey
- Safety Event
- Preventive Care Opportunity
- Access Event

The 33 base relationships form one connected graph. Patient, provider,
facility, service line, CMS measure, and reporting period entities connect
through domain events rather than through artificial direct associations.

| Domain event | Connected shared entities |
|---|---|
| Readmission Event | Patient, Provider, Facility, Reporting Period |
| Mortality Encounter | Patient, Provider, Facility, Reporting Period |
| Experience Survey | Patient, Provider, Facility, Service Line, Reporting Period |
| Safety Event | Patient, Provider, Facility, Reporting Period |
| Preventive Care Opportunity | Patient, Provider, Facility, CMS Measure, Reporting Period |
| Access Event | Patient, Provider, Facility, Reporting Period |

Provider also connects directly to Service Line using the governed
`service_line_key`. CMS measure results, benchmarks, and star assessments
remain connected through Facility, CMS Measure, and Reporting Period.

Domain teams should add analytical concepts, interventions, predictions, and
other domain-specific relationships in team-controlled artifacts rather than
redefining these shared event relationships.

## Governance boundaries

| Centrally governed | Team controlled |
|---|---|
| Table grains and keys | Domain-specific calculations |
| Conformed dimensions | Experimental measures |
| Published CMS values | Driver and root-cause methods |
| Official methodology references | Predictive models |
| Provenance labeling | Reports and user experiences |
| Shared names and descriptions | Agents and MCP tools |
| Certified model releases | Domain ontology extensions |

## Measure promotion

Teams can create experimental measures freely. A measure is promoted into a
certified shared model only when it has:

1. A clear business definition and owner.
2. A documented numerator, denominator, grain, and exclusions.
3. Correct synthetic or authoritative provenance.
4. Validation across facilities and reporting periods.
5. A unique name that does not conflict with an existing governed measure.

**Next:** [06 CMS Stars guidance](06_cms_stars.html)
