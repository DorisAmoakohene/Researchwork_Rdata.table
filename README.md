# Researchwork_Rdata.table

# DATA.TABLE

# Backup
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

