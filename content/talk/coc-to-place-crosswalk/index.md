---
title: "Bridging Homelessness and Census Data: A CoC-to-Place Geographic Crosswalk"
date: 2026-03-01
date_label: "Mar 2026"
authors: ["Tyan Lee"]
publication_types: ["presentation"]
publication: "Poster, Evidence, Experience, and Pathways: A Convening on Unsheltered Homelessness in L.A. (USC Homelessness Policy Research Institute and SIEPR)"
abstract: "Homelessness Point-in-Time (PIT) counts and Housing Inventory Counts (HIC) are reported at the Continuum of Care (CoC) level, while Census data on housing and economic conditions are reported at the county and place level. I construct a crosswalk linking CoC codes to Census place FIPS codes, enabling researchers and policymakers to merge these two critical data sources at the CoC level for every CoC in the nation."
tags: ["homelessness", "Continuum of Care", "data"]
home_blurb: "A CoC-to-place crosswalk I created to bridge census and homelessness data sources, presented as a poster at Evidence, Experience, and Pathways: A Convening on Unsheltered Homelessness in L.A. (USC HPRI and SIEPR, Mar 2026)."
research_areas: ["homelessness-policy"]
---

## Background

HUD's roughly 400 CoCs are the primary geographic unit for homelessness data collection and service delivery. However, CoC boundaries do not consistently correspond to any standard Census geography. Historically, therefore, researchers have been forced to pool CoCs to match county boundaries.

Researchers have taken various approaches to overcome this geographic complexity (see, for instance, concurrent work by Schachner and Gannon), but to my knowledge, there is currently no crosswalk that makes Census data available at the CoC level for every CoC in the U.S.

## The Crosswalk

Manual inspection of each CoC's boundaries using HUD documentation reveals that all CoC boundaries that do not align with Census county boundaries appear to be explained by Census place boundaries. I construct the crosswalk by applying county- and place-level inclusions and exclusions to handle CoCs whose boundaries do not follow county lines. Each row represents one CoC-county-place match and contains:

- `coc_code`: HUD Continuum of Care identifier
- `state_fips`: State FIPS code
- `county_fips`: County FIPS code
- `place_fips`: Census place FIPS code

## Per-Capita Homelessness

Unlike many other economic and demographic topics, even basic homelessness statistics have rarely been presented in per-capita terms below the state level, because previously it would have been challenging to measure the population of any CoC that does not happen to fall neatly within county lines. With the crosswalk in hand, PIT count data can now be merged with ACS place-level variables, facilitating novel research. In particular, I compute per-capita homelessness at the CoC level.

## Racial Disparities in Homelessness

The crosswalk also makes it possible to estimate relationships between homelessness, poverty, and other factors at a granular geographic level, capturing within-state heterogeneity and increasing statistical power. To illustrate this, I merge 2020–2024 ACS data with 2024 PIT counts and investigate how the relationship between poverty and homelessness differs by race.

As national statistics have long indicated, Black Americans experience homelessness at much higher rates than the broader U.S. population. I find that this is true in nearly every CoC. This may be partly attributable to the fact that Black Americans also experience poverty at higher rates than the broader population; again, this is the case in nearly every CoC. With poverty and homelessness rates now available at the CoC level, however, it is possible to confirm that Black Americans experience homelessness at higher rates than other racial groups, even conditional on poverty.

## Conclusions and Future Work

- The CoC-to-place crosswalk fills a longstanding gap in homelessness research and policy infrastructure.
- Researchers can now link PIT counts to ACS housing, poverty, and labor market variables at the CoC level.
- Policymakers can obtain Census data for their specific CoC, informing policy decisions.
- We are in the process of linking the FBI's Uniform Crime Reports (UCR) dataset to this crosswalk, allowing us to analyze existing variables in conjunction with crime incidence at the CoC level.
- Future work will modify the crosswalk to take into account CoC boundary changes, enabling longitudinal analysis and causal research.

## Acknowledgements

I would like to thank Derek Christopher and David Grusky for their extensive support and guidance throughout this project.
