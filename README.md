# stock-analysis

## Overview of Project

### Purpose

The initial purpose of the project was to help Steve write a script that calculated the total daily volume and the percent return for each of the 12 stocks that his parents were interested in following for the years of 2017 and 2018.  

Once the code was succefully writen to complete the analysis, the code was rewriten (refactored) to try to improve the time it took for the analysis to complete (for the code to run).

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

### Significant Code Refactoring that led to improved performance

The most important change made to the original code was to create a ticker index (```tickerIndex```) and 3 arrays: for the Stock ticker total daily Volume (```tickerVolumes```), for the starting price of the stock (```tickerStartingPrices```) and for the ending price of the stock (```tickerEndingPrices```).

## Summary

### Advantages and disadvantages of refactoring code in general
The advantages of refactoring code potentially include:
1. make code run faster,
2. make code easier to follow by adding additional comments,
3. make code easier to change and mantain by reducing duplicates.

The disadvantages of refactoring code potentially include:
1. It takes time to refactor code,
2. It may introduce bugs if not checked carefully.

### Advantages and disadvantages of refactoring the code to analyze stock
In this particular case refactoring of the code significantly improved the time it took to perform the stock analysis.  
A disadvantage of refactoring the code was that in an effort to make it run faster, I made a mistake where to introduce the statement to increase the tickerindex increase (```tickerIndex = tickerIndex + 1```) that led to a bug that took me 3 days to discover.

