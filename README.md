# stock-analysis

## Overview of Project

### Purpose
The initial purpose of the project was to help Steve write a script that calculated the total daily volume and the percent return for each of the 11 stocks that his parents were interested in following for the years of 2017 and 2018.  
Once the code was succefully writen to complete the analysis, the code was rewriten (refactored) to try to improve the time it took for the analysis to complete (for the code to run).

### Analysis of Outcomes Based on Launch Date
To analyze the relation between the outcome of a theater campaign and the date the campaign was launched I created a pivot table from the master data filtered to contain only data from theater campaigns for all years in the database.  The sum of the different outcomes were shown per month in rows.

![](resources/Table-theater-outcomes.PNG)

From this pivot table I produced a linechart with the sum of each of the possible outcomes on the y-axis and the month the campaign was launched on the x-axis:

![](resources/Theater_Outcomes_vs_Launch.png)

### Analysis of Outcomes Based on Goals
To analyze the relation between the initial goal set and the outcome for a play I created a table where I broke the down the goal into 12 different levels (rows) and then in 3 additional columns counted the total number of plays that were successful, that failed and that were cancelled per goal range.  To accomplish this, I used a COUNTIFS statement with 3 or 4 different conditions that needed to be met: 

1. campaign was for a "play" 
2. the goal of the campaign was larger or equal to the lowest value in the goal range, 
3. the goal of the campaign was smaller or equal to the highest value in the goal range,
4. the campaign outcome was defined as "success" (column B), "failed" (column C) or canceled (column D).


an example of a such statement: ```=COUNTIFS(Data!R:R,"plays",Data!$D:$D,">=25000",Data!$D:$D,"<=29999",Data!$F:$F,"Canceled")```

Once this was accomplished I calculated the percentage of plays that were succesfull (column F), failed (column G) and canceled (H) by dividing the number of each outcome by the total number of plays and formating the column to percentage.

Here is what the table looked like:

![](/Resources/Table-outcomes-goals.PNG)

Using this table I constructed a line graph where on the y-axis I plotted the percent of the campaigns that were successfull, failed and were cancelled and on the x-axis I ploted the campaign goal ranges:

![](resources/Outcomes_vs_Goals.png)


## Results

### Analysis of 2017 stock

The analysis shows that with the exception of the "TERP" stock, all stocks had a positive return for the year of 2017.  
The median return was 41.5% and the mean return was 67.3%.

With the refactored code, the time to run the analysis for the year of 2017 and generate the same results decreased ~4.9x from ~0.921875 seconds to 0.1875 seconds:

![](Resources/VBA_Challenge_2017.PNG)

### Analysis of 2018 stock

The analysis shows that in 2018 ten out of twelve stocks had negative returns.  
The median return was -12%. The mean return was -8.5%.
The only two stocks with positive returns were "ENPH" and "RUN" with returns of 81.9% and 84.0%.

With the refactored code, the time to run the analysis for the year of 2018 and generate the same results decreased ~3x from ~0.796875 seconds to 0.265625 seconds:

![](Resources/VBA_Challenge_2018.PNG)

## Summary

### Advantages and disadvantages of refactoring code in general
The advantages of refactoring code potentially include:
1. make code run faster,
2. make code easier to follow and to improve upon by adding additional comments,
3. remove bugs with original code and add improvements.

The disadvantages of refactoring code potentially include:
1. It takes time to refactor code,
2. It may introduce bugs if not checked carefully,
