# The Visible Breach

## Overview

This project analyzes public cybersecurity incident data from the **VERIS Community Database (VCDB)** to examine what public breach data can — and cannot — tell us about industry-level cyber risk.

The central argument of the project is that public breach data does not simply show where cyberattacks happen. It shows where incidents are **reported, discovered, and made visible**. The analysis develops this argument through two connected ideas: a **reporting gap** and a **detection gap**.

## Research Question

How do reporting obligations and discovery methods shape which cybersecurity incidents become visible in public breach data?

More specifically, this project asks:

1. Which industries appear most often in VCDB?
2. Do high-count industries tend to be industries with federal reporting obligations?
3. Do lower-volume sectors still show meaningful nation-state or state-affiliated actor activity?
4. How do industries differ in internal versus external discovery?
5. How does dwell time differ between internally and externally discovered incidents?

## Main Findings

The industries most visible in VCDB are concentrated in sectors such as **Healthcare, Public, Educational, Finance, and Information**. However, these counts should not be read as a direct measure of true attack frequency, because many of these industries also operate under broader federal reporting or disclosure obligations.

The actor-type analysis complicates the raw-count story. Several sectors with lower public record volume still show meaningful shares of state-linked external-actor incidents. This suggests that low public record volume should not automatically be interpreted as low strategic risk.

The detection analysis shows a second visibility problem: before an incident can be reported, it has to be discovered. Discovery methods vary across industries, and externally discovered incidents are associated with substantially longer dwell times than internally discovered incidents.

## Visualizations Included

This report includes five main visualizations:

1. **Total VCDB records by industry**  
   Shows which industries dominate the public record.

2. **VCDB records by reporting/disclosure regime**  
   Compares industry record counts with broad federal reporting obligations.

3. **State-linked actor share by industry**  
   Highlights industries where nation-state or state-affiliated activity appears more concentrated.

4. **Internal vs. external discovery by industry**  
   Shows how discovery methods differ across sectors.

5. **Dwell time by discovery method**  
   Compares how long incidents remain active before discovery, using a log-scaled boxplot.

## Data

The project uses the **VERIS Community Database (VCDB)**, a public cybersecurity incident dataset structured using the VERIS framework. The dataset used in this project contains **10,586 observations**, with each observation representing a reported cybersecurity incident.

Key variables used include:

- victim industry
- breach confirmation
- discovery method
- actor type
- external actor variety
- discovery timeline / dwell time

*The VCDB dataset used for this analysis is not included in the repository because the file exceeds GitHub’s 100 MB file-size limit. The analysis expects the file at:*

`data/vcdb.csv`

The rendered HTML report is included in `analysis/analysis.html`.

[VERIS VCDB dataset zip](https://github.com/vz-risk/VCDB/blob/master/data/csv/vcdb.csv.zip)

## Methods

The project uses R and Quarto, with visualizations created primarily through `ggplot2` and tidyverse workflows.

Main techniques include:

- categorical bar charts
- color encoding by disclosure regime
- proportional actor-type analysis
- stacked proportional bar charts
- log-scaled boxplots for skewed dwell-time data
- careful discussion of limitations and non-causal interpretation

## Limitations

VCDB is not a complete record of all cyber incidents. It is shaped by voluntary submission, public reporting, and legal disclosure obligations. The reporting-regime categories used in this project are broad constructed groupings and do not fully capture state-level breach notification laws, sector-specific rules, or enforcement differences. Actor-type coding may also be incomplete or uneven across incidents.

The analysis is observational and does not control for organization size, incident severity, year, or sector exposure. Therefore, the project does not make causal claims about why visibility differs across industries.
