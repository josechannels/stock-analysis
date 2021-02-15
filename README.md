# stock-analysis

## Overview of Project

### Purpose
The purpose of this project was to rewrite (refactor) the original code for the stock analysis that Steve prepared for his parents with the aim to run the code faster.

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

![](/resources/Table-outcomes-goals.PNG)

Using this table I constructed a line graph where on the y-axis I plotted the percent of the campaigns that were successfull, failed and were cancelled and on the x-axis I ploted the campaign goal ranges:

![](resources/Outcomes_vs_Goals.png)


## Results


