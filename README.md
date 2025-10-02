# Barley-Project
**This project summarizes my ability in data cleaning, plotting (histograms, charts, time series graph), regression analysis and interpretation of results. The data and guidelines for this project were provided by the Energy Policy Institute at the University of Chicago (EPIC) and are summarized below.**

## 1. Data Introduction
There are two CSV input datasets, briefly described below. These datasets are provided
in the .zip file and contain all the data that you will need. Each dataset is from the US
Department of Agriculture.
- Barley production.csv lists the barley production in bushels by agricultural districts. The agricultural district is an administrative division between the county and
state levels.
- Barley price.csv lists the mean price received by farmers per bushel of barley by
state. Ignore the distinction between the marketing year and the calendar year.
Each file contains annual data from 1990 to 2017.


## 2. Data Exploration (Plots and explanations in written summary)
### 2.1 Histograms
- Created six frequency histograms of agricultural district barley production, one for each of
the following years: 1990, 1995, 2000, 2005, 2010, and 2015
- Scaled the production variable so that it is in millions of bushels
- Kept observations that are between the 1st and 99th percentiles of barley production for a given year
- Colored the histogram bars based on the year: red (1990),orange (1995), yellow (2000), green (2005), blue (2010), and purple (2015)

### 2.2 Dataset Cleaning
- Collapsed Barley production.csv at the state-year level
- Set production equal to the sum of production across the state
- Scaled the production variable so that it is in millions of bushels
- Merged with Barley price.csv and kept only variables that will be used in the later
analyses

### 2.3 Time Series Plot
- For each year, computed the weighted average of price over all states, where each state’s
weight is its production in bushels in that year
- Plotted this weighted average over the time period from 1990 to 2017

### 2.4 Summary Table
- Created a summary table where the rows are specific states (Idaho, Minnesota, Montana,
North Dakota, and Wyoming) and the columns are decades (1990-1999, 2000-2009, and
2010-2017)
- The elements of the table are mean annual state-level production, by decade
and state

## 3. Short Answer (Adressed in written summary)
Our goal is to estimate the sensitivity of US farmers’ barley production to barley price, using
the provided data, at the level of state by year. Drop state years with missing production
data. Please provide all answers in the document and provide the best presentation you are
able to on your write-up.
  1. First write down the equation of a linear model of production on a constant and price.
Ensure that the terms are properly indexed.
  2. Estimate the linear model you’ve written in (1) using linear regression. (If you are
unable to run the regression, refer to Column 1 of Table 1.)
      - (a) What is the interpretation of the coefficient on price?
      - (b) Briefly describe one reason why we cannot interpret the coefficient as a causal
effect of price on production.
  4. What variables do you think we should control for? Choose two and explain why they
might help us to identify the causal effect of price on production. These variables need
not be in the original dataset.
  5. Regress production on price with state fixed effects. Cluster standard errors at the
state level. (If you are unable to run the regression, refer to Column 2 of Table 1.)
      - (a) Write down an equation for this model.
      - (b) What is the interpretation of the coefficient on price?
      - (c) State fixed effects include a constant for each state in the regression specification.
Illustrate how state fixed effects can account for state-specific characteristics that
do not change over time. Do you prefer this specification? Why or why not?
  6. We decide to use year fixed effects in addition to state fixed effects. Run this regression
on the provided data and report the estimated coefficient on price, along with its
standard error. Justify the method you used to calculate the standard error. (If you
are unable to run the regression, refer to Column 3 of Table 1.)
     - (a) Write down an equation for this model.
     -  (b) What is the interpretation of the coefficient on price?
     -  (c) Year fixed effects include a constant for each year in the regression specification.
Illustrate how time fixed effects can account for time-specific characteristics that
are the same across states. Do you prefer this specification? Why or why not?
  7. Suppose one of the other research assistants accidentally deletes 10% of the observations
of the barley production variable. How would you expect dropping these observations
to change the estimated coefficient on price and its standard error if the deletions are
random? What if they are not at random?
  8. Refer back to the estimated coefficients on price. Does our model uncover the true
relationship between price and supply as predicted by economic theory? Why or why
not?
