# Barley-Project
This data task was completed to illustrate my capability in data analysis to an internship application with the Energy Policy Insitute at the University of Chicago (EPIC). Specifically, this project summarizes my ability in data cleaning, plotting (histograms, charts, time series graph), regression analysis and interpretation of results. The following are the instructions for the project provided by EPIC.

## 1. Overview
This test is inspired by a recent EPIC research project. Your task is to perform basic data
cleaning, prepare a final dataset for analysis, provide short answers to prompts, and create
publication-quality figures. Submit the test on Canvas by the end of your testing window.
For the coding portion of this test, we will accept code in R, Stata, or Python. You are
welcome to use any pre-existing online programming or econometrics resources, but you
may not ask other people for help. In addition, you may not use generative AI for any part
of this data task e.g. you may not use ChatGPT. Data tasks that use ChatGPT will not be
graded.
If you are unsure of how to answer a question, feel free to answer to the best of your ability
with any ideas that come to mind. If you find any of these instructions to be confusing,
please proceed in a way that you find relevant and reasonable, and list your assumptions in
your writeup.
Please aim to show your best effort on the tasks. While the questions outline essential
requirements, feel free to go beyond them if you feel inspired. Two or three sentences should
suffice for each of your responses in the Short Answer section.
Once you have completed the sections below, please submit the following in a .zip file named
LASTNAME FIRSTNAME.zip:
- Code file(s)
- Final dataset
- Graphs
- Tables
- A short document with your responses to the questions named LASTNAME FIRSTNAME.pdf.

Data tasks will be evaluated based on the following criteria:
- Correctness
- Code clarity - code should be commented appropriately. The final folder should be
well-organized and files should have informative names.
- Document clarity - the final document should be neat. Tables and figures should be
publication-quality and answers should be clear and concise.
- Replicability - we should be able to produce all tables and figures with minimal changes
to your code.

## 2. Data Introduction
There are two CSV input datasets, briefly described below. These datasets are provided
in the .zip file and contain all the data that you will need. Each dataset is from the US
Department of Agriculture.
- Barley production.csv lists the barley production in bushels by agricultural districts. The agricultural district is an administrative division between the county and
state levels.
- Barley price.csv lists the mean price received by farmers per bushel of barley by
state. Ignore the distinction between the marketing year and the calendar year.
Each file contains annual data from 1990 to 2017.

## 3. Econometrics Background (ungraded)
In 1-2 sentences, please briefly describe your background in econometrics and statistics (e.g.,
coursework, research experience). If you have not yet taken econometrics, please note when
you intend to take an econometrics equivalent course and its course number at your university.


## 4. Data Exploration (40 Points)
### 4.1 Histograms
Create six frequency histograms of agricultural district barley production, one for each of
the following years: 1990, 1995, 2000, 2005, 2010, and 2015. Scale the production variable
so that it is in millions of bushels. Only keep observations that are between the 1st and 99th
percentiles of barley production for a given year. Ensure all plots have titles that include the
year. Save each file separately and label it “barley production histogram YEAR.pdf” where
YEAR is the appropriate year. Color the histogram bars based on the year: red (1990),
orange (1995), yellow (2000), green (2005), blue (2010), and purple (2015). These plots do
not need to appear in the final document.

### 4.2 Dataset Cleaning
Collapse Barley production.csv at the state-year level. Set production equal to the sum
of production across the state. Scale the production variable so that it is in millions of
bushels. Merge with Barley price.csv. Only keep variables that will be used in the later
analyses. Use this dataset for the remainder of the data task. In the document, write a brief
description of the dataset and any potential limitations that future users should be aware of
(3–4 sentences or less).

### 4.3 Time Series Plot
For each year, compute the weighted average of price over all states, where each state’s
weight is its production in bushels in that year. Then, plot this weighted average over the
time period from 1990 to 2017. Include this figure in the document and briefly describe the
trend. Note any changes to the sample across the years.

### 4.4 Summary Table
Create a summary table where the rows are specific states (Idaho, Minnesota, Montana,
North Dakota, and Wyoming) and the columns are decades (1990-1999, 2000-2009, and
2010-2017). The elements of the table are mean annual state-level production, by decade
and state. Include this table in the document.

## 5. Short Answer (60 Points)
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
