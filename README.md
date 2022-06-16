# Kickstarting with Excel

## Overview of Project

### Purpose
  For this challenge, our purpose was to look at Kickstarter data for plays launched and ended from 2014 - 2016.  Using tools within Excel, I wanted to determine if there was a correlation between the listed funding goal for a play Kickstarter and the likelihood that of the Kickstarter either succeeding or failing.  I also wanted to determine if there was a possible correlation between the launch date of a Kickstarter and the possibility of the funding goal being met.    

## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date
  The analysis of the outcomes based on launch date was done using tools within Excel to format the data for easier analysis.  I first took the outcome column of the Kickstarter dataset and added it into a pivot table.  I also filtered the data based on 'successful', 'failed', and 'canceled' outcomes.  I modeled the data using the date created column to compare against the outcome column.  The final chart was created using the pivot chart function to format the data points into line chart. ![Chart of Outcomes Based on Launch Date](https://github.com/mleiser/kickstarter-analysis/blob/main/resources/Theater_Outcomes_vs_Launch.png?raw=true)
  
### Analysis of Outcomes Based on Goals
  The analysis of the outcomes based on the Kickstarter funding goals was done through a combination of formulas, a pivot tables, and a pivot chart.  The formulas were used to pull in data based on a funding target range such as 1000 to 4999 or 5000 to 9999.  I was then looking for three things, the number of goals that were successful, the number that failed, and the number that were canceled.  An example formula to find there would look similar to this:
```
=COUNTIFS(Kickstarter!D:D, ">=10000", Kickstarter!D:D, "<=14999", Kickstarter!F:F, "successful", Kickstarter!R:R, "plays")
```
Each of the columns had functions similar to the above but with "successful" either replaced by "failed" or "canceled" depending on the column.  I then wanted to know the total projects for a range and the percentage of each point for every funding range.  The total was found by using the SUM function and the percentage was found with the following formula:
```
=(B2/E2)
```
with the formula changing depending on the outcome it was looking for.  The results were then added to a pivot table and then a line chart was created using the data points. ![Chart of Outcomes Based on Goals](https://github.com/mleiser/kickstarter-analysis/blob/main/resources/Outcomes_vs_Goals.png?raw=true)

### Challenges and Difficulties Encountered
  For difficulties when making doing this challenge, it's important to make sure to always be looking in the correct column with your formulas.  I had some trouble getting my chart for Outcomes vs. Goals to come out as it was supposed to for a while.  I later figured out that I had forgot to change the column for one of my formulas looking up the failed data point, and it was instead pulling the successful data.

## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?
  Based on the chart created by the data.  I can conclude that there is a better chance for a Kickstarter for a play to succeed when started in May, June, or July due to the sharp increase in successes during that month.  I can also conclude that there is no correlation between when a Kickstarter is launched vs. the likelihood for it to fail since the line did not trend in either direction to an appreciable degree.

- What can you conclude about the Outcomes based on Goals?
  Based on the chart for the Outcomes based on Goals, I can conclude that a Kickstarter is more likely to fail the higher the funding goal is. This is because the line for the successful campaigns trended downward overall as funding goals went up, while the line for failed goals trended upward at the same rate.

- What are some limitations of this dataset?
  Some limitations of the dataset is that it hasn't been cleared of outliers. An example of this would be in Outcomes based on Goals chart, it's possible to see that the 45000 to 49999 goal was all failed and not a single one succeeded.  The dataset also doesn't take into account low amounts of data such as the upper limits of the funding goals.  Those particular ranges had a much lower concentration of data than lower ranges and could have caused a skewed chart especially in the 35000 to 39999 and 40000 to 44999 ranges which had 6 and 3 total projects, respectivly. 

- What are some other possible tables and/or graphs that we could create?
  Some other tables that could be considered is something to look at a possible correlation between Outcomes vs. Country to see if there is any difference of successes in either the US or GB.  It would also be interesting to see a box and wisker plot between goal ranges and amount of backers to see if there is a relationship between funding goal ranges and the amount of backers. 
