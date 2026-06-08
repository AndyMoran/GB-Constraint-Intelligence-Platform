# Definitions and Terminology

## Purpose

This document defines the core concepts used throughout the GB Constraint Analytics Platform.

The objective is to ensure consistent interpretation across notebooks, reports and future research phases.

---

# Constraint Analytics Concepts

## Constraint Event

The smallest observable unit of transmission constraint activity.

A Constraint Event represents a period during which a transmission boundary experiences congestion requiring operational intervention.

Constraint Events are the raw observations from which higher-level operational structures are derived.

---

## Operational Episode

A collection of Constraint Events separated by less than a specified recovery-gap threshold.

Operational Episodes represent the practical operational challenge faced by flexibility assets.

An episode may contain multiple individual constraint events.

Throughout this project, Operational Episodes are treated as the primary unit of analysis for storage feasibility.

---

## Recovery Window

The elapsed time between the end of one Operational Episode and the beginning of the next.

Recovery Windows represent the opportunity available for a storage asset to recharge before the next operational challenge begins.

---

## Loading Ratio

A dimensionless measure of operational loading relative to observed transmission constraint conditions.

Loading Ratio is used throughout the project to compare constraint severity without relying on specific MW values.

---

## Burden

A measure of cumulative operational challenge.

In this project:

Burden = Loading Intensity × Duration

Burden is expressed in loading-hours.

Burden combines both the severity and persistence of constraint behaviour into a single metric.

---

## Sequence Amplification

The increase in operational burden caused by multiple events occurring in close temporal proximity.

Sequence Amplification quantifies how clustering transforms individual events into larger operational challenges.

Higher values indicate that clustering materially increases the difficulty faced by flexibility assets.

---

# Storage Feasibility Concepts

## Power Feasibility

A battery is Power Feasible when its maximum discharge capability exceeds the peak loading requirement of an Operational Episode.

Power Feasibility is evaluated before energy adequacy.

Failure at this stage prevents participation regardless of available stored energy.

---

## Static Failure

A failure caused by insufficient discharge capability.

The asset cannot satisfy the peak power requirement of an Operational Episode and therefore fails before meaningful participation occurs.

Static Failure represents a power limitation.

---

## Dynamic Depletion

A failure caused by exhaustion of stored energy during an Operational Episode.

The asset initially participates successfully but cannot sustain operation for the full duration of the episode.

Dynamic Depletion represents an energy limitation.

---

## Survivability

The ability of a storage asset to complete an Operational Episode successfully.

An asset survives when:

* Power requirements remain within asset capability.
* Energy requirements remain within available capacity.

Survivability is the primary performance metric used in the storage-feasibility analysis.

---

## Safety Margin

The difference between available recovery time and required recharge time.

Safety Margin = Recovery Window − Recharge Requirement

Positive values indicate that full recharge is achievable before the next episode begins.

Negative values indicate potential recharge risk.

---

# Conceptual Framework

## Pipe and Tank Framework

A visual framework used to explain storage feasibility.

### Pipe

Represents instantaneous discharge capability (Power).

The Pipe determines whether an asset can physically participate in an Operational Episode.

A larger Pipe allows participation in more severe events.

### Tank

Represents stored energy capacity (Energy).

The Tank determines how long an asset can continue operating once participation begins.

A larger Tank reduces Dynamic Depletion risk.

### Interpretation

Power acts as the first feasibility hurdle.

Energy becomes relevant only after power requirements have been satisfied.

---

# Research Methodology Concepts

## Representative Example

A single real-world example selected to illustrate a mechanism or operational process.

Representative Examples explain findings.

They do not, by themselves, constitute proof.

---

## Population Evidence

Evidence derived from the complete analysed population rather than from individual examples.

Population Evidence validates whether a finding generalises across the dataset.

Throughout the project, Representative Examples are typically paired with Population Evidence.

---

## Look-Ahead Bias

The use of information that would not have been available at the decision point being modelled.

Look-Ahead Bias can create unrealistically optimistic results and is prohibited in predictive modelling.

A core project principle is:

Time flows forwards.

---

## Walk-Forward Validation

A time-series validation technique in which models are trained on historical data and tested on later periods.

Example:

* Train: 2021–2023
* Test: 2024

followed by:

* Train: 2021–2024
* Test: 2025

Walk-Forward Validation is the preferred evaluation approach for predictive notebooks.

---

# Project Principles

## Physics Before Economics

Physical feasibility should be established before economic evaluation.

The preferred analytical sequence is:

Physical Burden
→ Capturable Burden
→ Revenue
→ Costs
→ Economics

---

## Power Before Energy

Storage assets must first satisfy power requirements before energy adequacy becomes relevant.

Static Failure therefore precedes Dynamic Depletion in the feasibility hierarchy.

---

## Episodes Before Events

Operational Episodes are the preferred unit of analysis when evaluating storage behaviour.

Individual events do not fully capture clustering, recovery requirements or operational challenge.

---

## Explain, Then Validate

A preferred project pattern:

Representative Example
→ Explain the mechanism

Population Evidence
→ Validate the finding

Both are required for robust conclusions.
