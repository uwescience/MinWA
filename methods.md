---
layout: page
title: Methods
image: 
caption: Photo by Eden Constantino
---

<img src="{{ site.url }}{{ site.baseurl }}/assets/img/methods.jpg">


**Data**

*What data sets are you using?*
Employment Security Data (ESD)  2010-2017
Geo encoded ESD 2010-2017
HUD Small Area Fair Market Housing Prices 2010/2011 - 2017
Imputed address and racial/ethnic dataset
Federal 2010 census data for the state of Washington

*What did you do to prepare the data?*
Read background material on data and explored work done by previous researchers, and inspected the raw data
Cleaned, wrangled, and merged data frames/tables of relevant variables
Just reading the data can take several hours!
Sometimes need to read overnight, in order to have access by the next day
PostgreSQL is also used to expedite data queries


**Tools (aka “component specification”)**

*What software packages, modules, etc. did you use?* 
R is the main analysis tool that is being used
-Haven, Dplyr, ggplot2, Graphhopper, and any other packages that will be helpful from R
Remote Git Server
PostgreSQL

*What are the dependencies between these and how did you render them interoperable?*
The many R packages used here were inherently interoperable. PostgreSQL also has an R Wrapper to read and write tables into the data frame for SQL queries. 
Outside packages/software needs to be requested and approved to be used in the enclave

**Processes**

*What does your workflow or pipeline look like?* 
- The demographic distribution of workers
  - Develop a definition and operationalize low wage workers
  - Disaggregate low wage workers by age, education, gender, and race
- Residential displacement (TBD) 
- Housing price burden (housing wage)
  - Identify public data through HUD
  - Clean and wrangle, create .csv file
  - Transfer .csv to enclave
  - Make housing wage variables
  - Use categories/bin WMLAD wage data
- Work commute burden
  - Merge Geo ESD and imputed address data 
  - Obtain de-identified home and work locations by using geocodes at the census tract level
  - Use interior points of census tract locations as input to graphhopper to obtain commute time and distance
  - Use maps for visualizations  
- What steps did you follow? 
  - We split into pairs to work on certain domains (i.e. residential displacement) but co-worked across the group

**Analyses**

*What approaches did you try that didn’t work?*

Initially, we considered some inferential analysis but decided that given the large nature of this dataset as well as the underexplored nature of residential displacement in the context of policies addressing income inequality, descriptive analyses would be most fitting.

Descriptive analyses allow us to describe and summarize the distribution of low-wage workers, and any patterns of residential displacement.  This can inform the types of inferential questions researchers ask, serving as the foundation for conducting further statistical data analysis. 


*What analyses did you end up sticking with?*

Overall, this project utilized exploratory data analysis 

  - The demographic distribution of workers, (WHO?)
      - Look at the distribution of low wage workers by race, gender, and age across the Puget Sound 

  - residential displacement, (WHAT?)
    - Aggregate measures:
        - Graphical visualization of the change in the composition of low-wage workers, white residents, college-educated at the census tract level over an 8-year period (2010-2018) 
    - Individual-level measures
        - Distribution of the number of the total number of moves over an 8-year period, also disaggregated by race, gender, age 
        - Distribution of the number of different numbers of moves disaggregated by race, gender, age

  - Housing price burden, and (HOW? WHY?)
      - Housing Wage
          - Rent price was 20,30,40,50,60 % of X monthly income, converted to hourly wage assuming 40/hrs per week per month
          - Select before/mid/after wage policy (years 2011, 2015, 2017), 2bedroom housing cost, and make 20-60% housing wage categories for rental price + hourly wage by zip code
          - Visualization of median SFMR’s/distributions 
          - Summary plot of median housing wage at 20-60% by zip code?
    - Housing Burden
        - Using quarter 2 hourly wages, categorize people as potentially housing burdened at 30, 40,50, and 60% given housing wage cut-offs by zip code
        - Try to visualize who is more/less housing burdened by zip code or distribution of housing burden
        - Potentially map these or leave for next folks to map
  - Work commute burden (HOW? WHY?)
      - Merging ESD and address data
      - Looking at the difference over time of commuting times and distances when before and after the minimum wage was enacted
      - Help get an idea if certain workers were additionally burdened by their commute


**Limitations**

*What are the shortcomings of your approach?*

- Because we are looking at descriptive statistics, we are limited by the claims we can make (particularly inferential claims)
- Any claims we make as a team may be qualified with several assumptions given that we don’t fully understand all aspects of the data
- The sensitive nature of the data will also limit our ability to provide a completely transparent description of all processes; other than to future WMLAD users

*How can your work be improved?*

- Writing cleaner, more efficient code 
- A set of clear and vetted procedures for version control within the enclave. The version control workflow has been an iterative process - trial and error.. 
- Exploration with the data is a massive undertaking and would likely require a lot more time and effort to gain a better understanding. 
- More domain experts with the administrative data would be beneficial
- More exposure to experts in mapping/data viz specific to our topic
- Future fellows/researchers can strive to provide visuals/deliverables specifically for organizations doing work around min wage/gentrification/displacement (asking stakeholders how we can be useful to them)
