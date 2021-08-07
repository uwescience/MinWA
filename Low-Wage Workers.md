---
layout: page
title: Low-Wage Workers
---

**Context**

This project examines the extent to which Seattle’s \$15 minimum wage policy affected low-wage workers on several dimensions - residential displacement, housing burden, and commute burden. The first step we needed to take to answer this question was to define and operationalize low-wage workers. There are several theories concerning what constitutes a low-wage worker. For example, previous minimum wage studies have used a $13 cutoff. Further, advocacy groups, such as [Dismantle Poverty in Washington](https://dismantlepovertyinwa.com/) suggest a person living in Washington making less than or equal to 200% more of the federal poverty line is considered low-wage. For our analysis, we decided to use a \$19/hour cutoff. Meaning, anyone making less than \$19/hour is considered a low-wage worker. We agreed on a \$19/hour cutoff based on previous Seattle minimum wage work done by [Jardim et al., 2017]( https://www.nber.org/system/files/working_papers/w23532/w23532.pdf)

We determined the low-wage worker variable by summing individuals’ total wages and hours worked (including if they had multiple places of employment) and dividing their total wages by their total hours worked to determine their hourly wage. Next, we created a low-wage variable that marked an individual as low-wage if they made less than \$19/hour or not low-wage if they made \$19/hour or more. 

**Preparing Data**

Below is an example of the code we used to create the low-wage variable

```
library(dplyr)

# Create new variables for individuals who have multiple jobs
esd_2010_17 <- esd_2010_17 %>% 
group_by(uniqueid) %>% 
mutate(totalhours = na_if(totalhours, 9999),
totalwages_sum = sum(totalwageamount),
totalhours_sum = sum(totalhours))

# Determine hourly Wage
esd_hourly <- esd_2010_17 %>% 
filter(total_hours != 0 & totalhours_sum) %>% 
mutate(hourlywage_sum = totalwages_sum/totalhours_sum,
hourlywage = totalwageamount/totalhours)

# Create Low-wage Variable for people making less than $19/hour
esd_hourly %>% 
mutate(low_wage = 
if_else(hourlywage_sum >= 19, 0,1))
```

**Visualizations**

