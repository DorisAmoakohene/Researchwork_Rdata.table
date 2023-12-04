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

## Description:
This repository aims to investigate performance regressions in the data.table package by examining its history, creating relevant performance tests, and using atime to analyze the performance of different code branches (before regression, regression, fix regression). Additionally, it provides a GitHub Action called r-asymptotic-testing that allows you to perform asymptotic testing on your data.table repository package upon every push/pull request.

## User Guide
# To Start:

1. To begin, conduct the atime test for the different code branches (before regression, regression, fix regression) to identify potential performance issues. [Here](https://github.com/DorisAmoakohene/Researchwork_Rdata.table/blob/main/Performance%20regression%20with%235424.Rmd) is an example of how to perform the atime test

  NB: Set up the necessary environment and dependencies, ensuring that the data.table package and the atime package are installed and loaded.

2. Generate a plot to showcase the fixes made in the data.table package using the atime package. Utilize the `atime_versions` function to track the fixes across different versions. Pass the following named arguments to `atime::atime_versions`: N, setup, expr, and the different code branches. More documentation of the atime package can be found [here](https://github.com/tdhock/atime/blob/compare-dt-tidy/man/atime_pkg.Rd). The documentation provides detailed information on how to use the atime package for performance analysis and tracking changes across different versions

3. Use the `plot` function to visually represent the execution times of the expression evaluated across different versions of the data.table package.

4. Run the GitHub Action by writing tests in `inst/atime/tests.R`. Define `test.list` as a list with names corresponding to different tests. Each element should be a list with named elements N, setup, expr, to be passed as named arguments to `atime::atime_versions`.  For further elaboration on the process of performing asymptotic time testing using the atime package, please refer to [this](https://github.com/marketplace/actions/r-asymptotic-testing)

# Example Usage

A. Provide links to the issue(s) comment(s) containing the original code(s) that reported the regression. If there are multiple issues with code exhibiting the regression, include links to each issue along with a summary of the observed symptoms in your own words.

B. Link to the pull request (PR) that caused the regression. Explain the cause of the performance regression in the data.table code using your own words.

C. Link to the PR that fixed the regression. Describe the changes made to fix the regression in your own words.

D. Provide links to your atime test code(s) and plot(s) that illustrate the performance regression and its fix. If there are multiple issues with code exhibiting regressions, include links and plots for each issue.

- R atime code file(s) 
- png atime figure file(s)

# Inputs:
- Links to the issue(s) comment(s) with the original code(s) reporting the regression.
- Link to the pull request (PR) that caused the regression.
- Link to the PR that fixed the regression.
- Links to the atime test code(s) and plot(s) illustrating the performance regression and its fix.

# Outputs:
- Visualizations of the performance regressions and fixes.
- GitHub Action report indicating the results of asymptotic testing on the data.table repository package.




## Performance Regression Analysis
# 1. 
   
   A. discusses regression: this link discusses the issue of Performance Regression with .N and := [issue5424](https://github.com/Rdatatable/data.table/issues/5424) other issues that was discussed includes [issues5366](https://github.com/Rdatatable/data.table/issues/5366) Significantly slower performance time-based rolling and [issue5371](https://github.com/Rdatatable/data.table/issues/5371)Memrecycle Performance Regression.
These issues address performance-related concerns and propose potential fixes or improvements to the data.table package
   
   B. The cause of the regression is related to the addition of the snprintf function in the assign.c.
   [CausesRegression](https://github.com/Rdatatable/data.table/pull/4491)
   
   C. The Regression was fixed by creating targetDesc function and adding snprintf in assign.c
   [Fixes Regression](https://github.com/Rdatatable/data.table/commit/e793f53466d99f86e70fc2611b708ae8c601a451)

   D.
   [link to my atime code](https://github.com/DorisAmoakohene/Researchwork_Rdata.table/blob/main/Performance%20regression%20with%235424.Rmd)

   [link to plot#issues5424](https://github.com/DorisAmoakohene/Researchwork_Rdata.table/blob/main/atime.list%20plot/atime.list.png)
   
   [link to plot#issues5366](https://github.com/DorisAmoakohene/Researchwork_Rdata.table/blob/main/atime.list.2.png)
   
   [link to plot#issues5371](https://github.com/DorisAmoakohene/Researchwork_Rdata.table/blob/main/atime.list%20plot/atime.list.3.png)


  # 2.
 A. This issue reported a  performance regression when performing group computations, specifically when running R's C eval on each group (q7 and q8) in the db-benchmark, indicating a  slowness in the implementation of the code.[link to comment that reported Regression](https://github.com/Rdatatable/data.table/issues/4200)
  

 B. This is the [PR]( https://github.com/Rdatatable/data.table/pull/4558) that discusses the 
Cause of the Regression: [The regression was specifically related to the evaluation of C code within each group of data, specifically q7 and q8 in the "db-benchmark"](https://github.com/Rdatatable/data.table/issues/4200#issue-555186870)  which appears that the regression occurred during the evaluation of C code within these particular groups, indicating a performance issue or slowness in the implementation of the code.

C. Fixed:  
[The regression was fixed Regression by the addition of const int nth = getDTthreads]( https://github.com/Rdatatable/data.table/pull/4558/files)

D.
[link to my atime code](https://github.com/DorisAmoakohene/Researchwork_Rdata.table/blob/main/groupby%20with%20dogroups%20(R%20expression)%20performance%20regression%20%234200.Rmd)

[Link to my atime plot for this Regression](https://github.com/DorisAmoakohene/Researchwork_Rdata.table/blob/main/atime.list%20plot/atime.list.4200.png)


# 3.
A. This issue reported that when using the dt[selector, foo := bar] syntax  with an index defined, the performance of that operation can be significantly slower compared to when there is no index.[Major performance drop of keyed := when index is present #4311](https://github.com/Rdatatable/data.table/issues/4311)

B. [Causes Regression](https://github.com/Rdatatable/data.table/issues/4311
) The regression  was caused by utilizing the ":=" operator with an index present while modifying data by reference.

C. [Fixes Regression by passing shallow(dt.s4) to the isS4() function](https://github.com/Rdatatable/data.table/pull/4440)

D. [Link to my atime code showing this Regression](https://github.com/DorisAmoakohene/Researchwork_Rdata.table/blob/main/Remove%20deep%20copy%20of%20indices%20from%20shallow.Rmd)

[link to my graph visualiazing my code](https://github.com/DorisAmoakohene/Researchwork_Rdata.table/blob/main/atime.list%20plot/atime.list.4440.png)


# 4. 
low performance of setkey function for version 1.12.0 and later #4788

A. [Link to the PR that discusses and reported the regression](https://github.com/Rdatatable/data.table/issues/4788)

B. [Link to the cause of the Regression](https://github.com/Rdatatable/data.table/issues/4788#issue-733285904). This Regression was caused due to the utilization of the setkey Function.  The issue lies in the substantial difference in execution time observed when utilizing the setkey function from different versions of the data.table package across various computer settings.

C. This Regression is still open and yet to be fixed

D. I am using this atime code to try and Reproduce a graph showing [the Regression and Before Regression of the issue](https://github.com/DorisAmoakohene/Researchwork_Rdata.table/blob/main/%23low%20performance%20of%20setkey%20%234788.Rmd).


# 5.

A. This Regression was reported in [join operation almost 2 times slower #3928](https://github.com/Rdatatable/data.table/issues/3928)

B. [This was caused by the implementations of newer version of R from 3.6.1, causing the slow](https://github.com/Rdatatable/data.table/issues/3928#issuecomment-651408089)

C. This Issue is still Opened

D.[This is the link to my atime code](https://github.com/DorisAmoakohene/Researchwork_Rdata.table/blob/main/join%20operation%20almost%202%20times%20slower.Rmd)


# 6.

A. 
[groupingsets() adding an extra column with named vectors? #5206]( https://github.com/Rdatatable/data.table/issues/5206)
This issue was by [Backport str2lang #4712]( https://github.com/Rdatatable/data.table/pull/4712)

B. This issue was caused by the introduction of the 
[parse(text=.)](https://github.com/Rdatatable/data.table/pull/4712)

C. This PR Fixes Regression by adding[if (length(names(by))) by = unname(by)](https://github.com/Rdatatable/data.table/pull/5227/files)

D.

# Efficiency of the Data.Table and other Packages
This aspect of the project aims to enhance the atime compare-data.table-tidyverse vignette by conducting an efficiency analysis of data.table and popular R packages such as Polar, collapse, dplyr, baseR, and Reshape. 

The objective is to provide users with optimized data manipulation techniques and enable them to make informed choices for efficient data processing within the R ecosystem."

This is a link to all the [codes](https://github.com/DorisAmoakohene/Researchwork_Rdata.table/blob/main/vignette%20atime%20data.t.Rmd) performing this analysis

## Plot

In this file, I conducted a comparison between data.table's CSV writing capabilities and other R packages such as readr, arrow, polars, and BaseR. The objective was to assess the performance and efficiency of these packages when it comes to writing CSV files in R
1. [Writing CSV files ](https://github.com/DorisAmoakohene/Researchwork_Rdata.table/blob/main/png/gg.write.png) 

2. [Reading CSV Files](https://github.com/DorisAmoakohene/Researchwork_Rdata.table/blob/main/png/gg.read.png) 

In this analysis, I  examined the efficiency of summarizing data by group using data.table and various other packages including dplyr, stats, summarytools, psyc, and plyr. The goal was to compare the performance and effectiveness of these packages in performing group-wise data summarization tasks.

3. [Summarizing by Group](https://github.com/DorisAmoakohene/Researchwork_Rdata.table/blob/main/png/ml.gg.png)

4. [Summarize by group, expanded](https://github.com/DorisAmoakohene/Researchwork_Rdata.table/blob/main/png/ml.exp.gg.png)


Conducted a comparison of data reshaping techniques between data.table and other packages such as Stats Reshape and tidyr. The focus was on evaluating the efficiency and effectiveness of these packages in transforming data between wide and long formats, enabling users to make informed choices based on their specific data reshaping needs.

5. [Reshaping wide to long ](https://github.com/DorisAmoakohene/Researchwork_Rdata.table/blob/main/png/ml.reshape.png)

6. [Reshaping Long to wide](https://github.com/DorisAmoakohene/Researchwork_Rdata.table/blob/main/png/ml.wide.png)

This shows the comparison of creating data frames in R using data.frame, data.table and tibble in dplyr

7. [Creating dataframe](https://github.com/DorisAmoakohene/Researchwork_Rdata.table/blob/main/ml.create.png)
