---
layout: page
title: Methods
---
<img src="{{ site.url }}{{ site.baseurl }}/assets/img/methods_pic.jpeg">

**Data** 

Data was provided by several Washington State agencies to create the Washington Merged Longitudinal Administrative Data (WMLAD); we also used federal data to help in our analysis. Each dataset was subsetted for years 2010 to 2017. After examining the  WMLAD data, it was revealed there were too many inaccuracies with the 2017 data. As a result, our analysis only examined years 2010 to 2016. Further, due to missing data, race and address data were imputed using Bayesian Improved Surname Geocoding Algrorithm. This was necessary to examine the differences of low-wage workers by race. 

To prepare the data for analysis, we read background information of the data and reviewed previous minimum wage research. Further, we inspected the raw data then cleaned, wrangled, and merged the data frames/tables of relevant variables. PostgresSQL was used to expedite data queries. 

<html>
<head>
<style>
table {
  font-family: arial, sans-serif;
  border-collapse: collapse;
  width: 100%;
}

td, th {
  border: 1px solid #dddddd;
  text-align: left;
  padding: 8px;
}

tr:nth-child(even) {
  background-color: #dddddd;
}
</style>
</head>
<body>

<h3>Data Sources</h3>

<table>
  <tr>
    <th>Agency</th>
    <th>Key Information</th>
    <th>Number of Observations</th>
  </tr>
  <tr>
    <td>Employement Security Data (ESD)</td>
    <td>Earnings, hours worked, job characteristics</td>
    <td>106,704,421</td>
  </tr>
  <tr>
    <td>Department of Social and Health Services (DSHS)</td>
    <td>Race/Ethnicity, Sex, Age, Residential Address</td>
    <td>700,000,000</td>
  </tr>
  <tr>
    <td>Department of Health</td>
    <td>Race/Ethnicity,Sex, Age, Residential Address</td>
    <td>200,000,000</td>
  </tr>
  <tr>
    <td>Housing and Urban Development (HUD)</td>
    <td>Fair Market Rent Prices</td>
    <td>15,155</td>
  </tr>
</table>

</body>
</html>


**Tools**

*Software packages, modules, etc.* 

Rstudio was our main analysis tool.
- We utilized several tidyverse packages, such as haven, dplyr, tidyr, and ggplot2. 
- Graphhopper is another R package we used to analyze commute burden
- Remote Git Server was used throughout our collaborative workflow
- PostgreSQL was used to expedite merging and wrangling large datasets

*Dependencies between software, packages and modules that were interoperable*

The many R packages used here were inherently interoperable. PostgreSQL has an R Wrapper to read and write tables into the data frame for SQL queries. Because of the sensitivity of the data, outside packages/software were either approved or denied upon request from the enclave administrator. 

**Processes**

*Workflow* 
- Demographic Distribution of Workers
  - Develop a definition and operationalize low-wage workers
  - Disaggregate low-wage workers by age, gender, and race
  - Visualize dstribution of low-wage workers 
- Residential Displacement (TBD) 
- Housing Price Burden 
  - Identify public data through HUD
  - Clean and wrangle data
  - Create and transfer .csv to enclave
  - Make housing wage variables
  - Use categories/bin WMLAD wage data
- Work Commute Burden
  - Merge Geo ESD and imputed address data 
  - Obtain de-identified home and work locations by using geocodes at the census tract level
  - Use interior points of census tract locations as input to graphhopper to obtain commute time and distance
  - Create geospatial visualizations  

<img src="{{ site.url }}{{ site.baseurl }}/assets/img/WAMAP.png">


**Analyses**

*Initial Ideas*

We initially considered doing inferential analyses. However, we decided descriptive analyses would be most fitting, given the extensive nature of the WMLAD dataset and the underexplored nature of residential displacement in the context of policies addressing income inequality.

Descriptive analyses allow us to describe and summarize the distribution of low-wage workers and any patterns of residential displacement. This can inform the types of inferential questions researchers ask, serving as the foundation for further statistical data analysis.

*Final Analyses*

This project utilized exploratory data analysis 

  - Demographic Distribution of Workers
      - Combine ESD data from 2010-2016 
      - Merge ESD data to imputed demographic data 
      - Create several low-wage variables based on different theories
      - Examine the distribution of low-wage workers of the different low-wage variables
      - Determine which low-wage variable to use 
      - Visualize the distribution of low-wage workers by race, gender, and age across the Puget Sound

  - Residential Displacement
      - Aggregate measures:
        - Visualize the change in composition of low-wage workers disaggregated by race at the census tract from 2010-2016 
      - Individual-level measures:
        - Examine distribution of the total number of moves from 2010-2016 disaggregated by race, gender, and age 
        - Examine distribution of the number of different numbers of moves disaggregated by race, gender, age

  - Housing Price Burden
      - Rent price was 20,30,40,50,60 percent of monthly income, converted to hourly wage assuming 40/hrs per week per month
      - Select years 2011, 2015, 2016 and 2 bedroom housing cost to make a 20-60% housing wage categories for rental price + hourly wage by zip code
      - Visualize fair market rent distribution 
      - Use quarter 2 hourly wages to categorize people as housing burdened
      - Visualize who is more/less housing burdened geographic region
        
  - Work Commute Burden
      - Merge ESD and address data
      - Examine the difference over time of commuting times and distances when before and after the minimum wage was enacted
      - Discern if certain workers were additionally burdened by their commute


**Limitations**

We can make limited claims, particularly inferential claims, because we examined descriptive statistics. As a result, the claims we make are qualified with several assumptions. The sensitive nature of the data also limits our ability to provide a completely transparent description of all processes; other than to future WMLAD users

*Potential Improvements*

- Writing cleaner, more efficient code 
- A set of clear and vetted procedures for version control within the enclave. The version control workflow has been an iterative process 
- Exploration with the data is a massive undertaking and would likely require more time to understand the data better. 
- More domain experts with the administrative data would have been beneficial
- Future fellows/researchers can strive to provide visuals/deliverables specifically for organizations doing work around the minimum wage, gentrification, and/or displacement 
