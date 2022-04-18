# Kickstarting with Excel

## Overview of Project

### Purpose

The purpose of this challenge was to investigate how the outcomes of Kickstarters in the provided dataset were affected by their launch dates and funding goals and to visualize those realtionships.

## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date

A "Years" column was created in the Kickstarter spreadsheet by applying the YEAR() function to based on the "Date Created Conversion" column. A pivot table was created using months from "Date Created Conversion" as rows and outcomes as columns/values, with filters for parent category and years. The parent category filter was set to "Theater" and outcomes were sorted in descending order.
![Launch Date Pivot Table](/resources/Launch_Date_Pivot.png)
A line chart was then created from this pivot table.
![Outcomes vs Month Line Graph](/resources/Theater_Outcomes_vs_Launch.png)

### Analysis of Outcomes Based on Goals

A new sheet was created with the columns "Goal", "Number Successful", "Number Failed", "Number Canceled", "Total Projects", "Percentage Successful", "Percentage Failed", and "Percentage Canceled". Rows were created to cover various ranges of goal amounts. The COUNTIFS() function was used to populate the "Number Successful," "Number Failed," and "Number Canceled" columns, based on the project outcome, the goal ranges, and the subcategory "plays". The SUM() function was used on each row to add the "Number Successful," "Number Failed," and "Number Canceled" columns to populate the "Total Projects". The percentages of successful, failed, and canceled projects by dividing the "Number Successful," "Number Failed," and "Number Canceled" columns by the "Total Projects" column.
![Goals Pivot Table](/resources/Goals.png)
A line chart was then created from this pivot table.
![Outcomes vs Goals Line Graph](/resources/Outcomes_vs_Goals.png)

### Challenges and Difficulties Encountered

When populating the pivot table rows with "Date Created Conversion", Excel will automatically split the data into Months, Quarters, and Years. Since we are only interested in Months, we must manually discard the other fields. There were no canceled Kickstarters in October, resulting in a blank entry in the pivot table as well as a break in the line graph. We could have fixed this using the Pivot Table Option "Show empty cells as: 0", but the directions ignored this. 

## Results

The most successful Kickstarters in the "Theater" category were launched in May. The fewest Kickstarters were launched in December. "Play" Kickstarters were more likely to succeed the lower their goals were. The exception to this rule was for goals between $35,000 and $44,999, however, with only 9 total projects in this range, this could just be a fluke. The lack of data points for higher goals is one limitation of this dataset. The data also ends at 2017, so if trends have changed recently it will not reflect this. Although we looked at outcomes based on the month of the launch date, it might also be useful to look at the outcomes by year, to see if theater Kickstarters are trending up or down over time. The Outcomes vs Goals could be improved by plotting exact data points rather than using ranges (we could exclude goals over $30,000 to keep the x-axis scale reasonable) and applying a trendline. This would allow Louise to target a specific chance of success and find the corresponding goal amount.
