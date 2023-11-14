# Researchwork_Rdata.table
A. link to the issue(s) comment(s) with original code(s) that reported the regression. (more than one if there was more than one issue with code that exhibits the regression) summary of symptom(s) in your own words.

B. link to PR which caused the regression. what was the cause of the performance regression in the data.table code? (in your own words)

C. link to PR which fixed the regression. what was changed to fix it? (in your own words)

D. link to your atime test code(s), and plot(s) which lets us see the performance regression and fix. (more than one if there was more than one issue with code that exhibits the regression)
- R atime code file(s) 
- png atime figure file(s)

1. Performance regression with .N and := #5424
   
   A. [discusses regression](https://github.com/Rdatatable/data.table/issues/5424)
   
   B. [CausesRegression](https://github.com/Rdatatable/data.table/pull/4491)
   
   C. [fixesRegression by by creating targetDesc function and adding snprintf in assign.c](https://github.com/Rdatatable/data.table/commit/e793f53466d99f86e70fc2611b708ae8c601a451)

   D.[link to my atime code](https://github.com/DorisAmoakohene/Researchwork_Rdata.table/blob/main/Performance%20regression%20with%235424.Rmd)
   [link to my plot](https://github.com/DorisAmoakohene/Researchwork_Rdata.table/tree/main/atime.list%20plot)



     
