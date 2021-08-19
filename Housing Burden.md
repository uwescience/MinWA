---
layout: page
title: Housing Burden
---
**Context**

The WMLAD data does not include data regarding how much money workers are spending on rent each month. However, in examining the effects of the \$15 minimum wage ordiance, housing costs are of particular importance. Thus, we utilized publicly available data from Housing and Urban Development (HUD) Small Area Fair Market rental prices for select zipcodes in the Puget Sound Region to estimate workers that are likely to be rent burdened. We defined rent burden as paying 30% or more of earnings on rent. 



<img src="{{ site.url }}{{ site.baseurl }}/assets/img/hud_gif.gif">

**Preparing Data**

Below we outline general steps we took to create these visuals. However, for full details please see our Github page for code. 

- Find public HUD data, subset for WA state and clean data to import to enclave
- Calculate changes in rent distributionsa cross time
- Calculate housing wage variables (hourly wage when spending 30-60 % of hypothetical monthly income on rent)
- Subset only years 2011,2015,2016 (before, at, after Minimum Wage Ordinance)
- Subset to only one bedroom for estimating rent burden
- Merge with subset of WMLAD data that includes geolocation ID's, zip code, unique ID, hourly wages, hours worked, and summed hours worked and wages for individuals with multiple jobs
- Make data frames to make each map
- Produce maps using shapefiles and ggplot2

**Visualizations**

We found that in 2011 when the state minimum wage was \$8.67/hr, nearly 100% of low-wage workers in the Puget Sound region were likely rent-burdened.

<img src="{{ site.url }}{{ site.baseurl }}/assets/img/Final Presentation_Outline.jpg"> 

Conversely, in 2016, when the state minimum wage was $9.47/hr, there was a reduction in the proportion of low-wage workers who were rent burdened in the Seattle area and an apparent increase in rent-burdened low-wage workers in the outermost zipcodes. One explanation for this is that increases in the minimum wage were helping low-wage workers to pay rent. Alternatively, low-wage workers were moving out of the city during this time and were priced out of the housing market.

<img src="{{ site.url }}{{ site.baseurl }}/assets/img/Final Presentation_Outline (1).jpg"> 
