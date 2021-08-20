---
layout: page
title: Residential Displacement
---

**Context**

We investigated ways others have measured displacement. Residential displacement – the involuntary residential mobility of an individual from their home – is difficult to measure, and there are different approaches from the literature.  For example, some population-based approaches measure compositional changes in a neighborhood/geographic area, usually based on demographic variables such as income or race.  The loss in population across these demographic categories is an indicator of displacement. A limitation of these measures is that actual mobility is not traced; thus, one cannot be sure if the loss in population across the demographic category are due to households leaving an area or a change in the demographic variable itself (e.g. increased income).

One way to address the limitations of population-based approaches is to use individual level data to identify increases in mobility, such as number of moves. Increased number of moves serves as a potential indicator of displacement. In accordance with this literature, we took a looked at how many times Seattle workers have ever moved between 2010-2017 as a way of beginning to understand displacement.

**Preparing Data**

Here are the general steps we took to prepare this data for analysis:
  - Reshape WMLAD address data, collected monthly from 2010 - 2017 into long format
  - Create a variable of the lagged address, i.e. address from the previous month for each uniqueID in the dataset
  - Calculate whether move occured by noting 1 if lagged address and current address are different, 0 if lagged address and current address are the same
  - Aggregate move over all years 
  - Subset data to only Seattle workers
  - Merge data with WMLAD wages data, in order to see differences in moves by worker type (Low-wage vs Non low-wage)
  - Build data frame for visualization of total moves

**Visualizations**

<img src="{{ site.url }}{{ site.baseurl }}/assets/img/Total_Moves_SeattleWorkers.png"> 
