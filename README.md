# Researchwork_Rdata.table

# DATA.TABLE

# Expanding the Open-Source Ecosystem for the R data.table Package

This project, funded by the NSF under th POSE is aiming to enhance the opensource surrounding the R data.table package.

data.table is a powerful R package that provides an enhanced version of the traditional data.frame object. It is designed for efficient data manipulation, particularly for large datasets.

 ## Objective
 
 1. Documentation Enhancement
 2. Community Engagement
 3. Bug fixes and Performance Regression Optimization
 4. Package Extension

## My Expected Outcomes

A more stable and optimized data.table package, with improved performance and usability.

## Performance Regression Analysis in the data.table Package

A. link to the issue(s) comment(s) with original code(s) that reported the regression. (more than one if there was more than one issue with code that exhibits the regression) summary of symptom(s) in your own words.

B. link to PR which caused the regression. what was the cause of the performance regression in the data.table code? (in your own words)

C. link to PR which fixed the regression. what was changed to fix it? (in your own words)

D. link to your atime test code(s), and plot(s) which lets us see the performance regression and fix. (more than one if there was more than one issue with code that exhibits the regression)
- R atime code file(s) 
- png atime figure file(s)

## Performance Regression Analysis
1. 
   
   A. discusses regression: this link discusses the issue of Performance Regression with .N and := [issue5424](https://github.com/Rdatatable/data.table/issues/5424) other issues that was discussed includes [issues5366](https://github.com/Rdatatable/data.table/issues/5366) Significantly slower performance time-based rolling and [issue5371](https://github.com/Rdatatable/data.table/issues/5371)Memrecycle Performance Regression.
These issues address performance-related concerns and propose potential fixes or improvements to the data.table package
   
   B. The cause of the regression is related to the addition of the snprintf function in the assign.c. [CausesRegression](https://github.com/Rdatatable/data.table/pull/4491)
   
   C. The Regression was fixed by creating targetDesc function and adding snprintf in assign.c [Fixes Regression](https://github.com/Rdatatable/data.table/commit/e793f53466d99f86e70fc2611b708ae8c601a451)

   D.[link to my atime code](https://github.com/DorisAmoakohene/Researchwork_Rdata.table/blob/main/Performance%20regression%20with%235424.Rmd)

   [link to plot#issues5424](https://github.com/DorisAmoakohene/Researchwork_Rdata.table/blob/main/atime.list%20plot/atime.list.png)
   [link to plot#issues5366](https://github.com/DorisAmoakohene/Researchwork_Rdata.table/blob/main/atime.list%20plot/atime.list.2.png)
   [link to plot#issues5371](https://github.com/DorisAmoakohene/Researchwork_Rdata.table/blob/main/atime.list%20plot/atime.list.3.png)



     
