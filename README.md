

# Performance-Report
## Project Overview

1.  ### Project Introduction
      ##### Project Objective:
  The objective of this report project done in Power BI is to leverage data visualization and analytics to provide comprehensive insights into key performance     
  indicators (KPIs) and metrics, enabling informed decision-making. 
  
  This project aims to transform raw data into meaningful visual reports that can be easily interpreted and   
  acted upon by stakeholders.


2.  ### Project Components
     ##### Data Source:
    The data is sourced from a public GitHub repository.

     ##### Base Measures: Aimed at getting the overall insights about the data.
    1.       sales = SUM(fact_sales[Sales_USD])
    2.       cogs = SUM(fact_sales[COGS_USD] )
    3.       quantity = SUM(fact_sales[quantity] )
    4.       gross_profit = [sales]-[cogs] 

    ##### Previous-Year-To-Date(PYTD) Measures :

    Aimed at comparing the performance of the current year to the same period in the previous year.

    This allows businesses to understand how their performance has changed year-over-year and identify trends, seasonality, and areas for improvement.

    By evaluating the same period in both years, PYTD measures provide a more accurate comparison by accounting for seasonal variations and other time-specific factors.
    
     1.         prior_YTD_sales = CALCULATE([sales],SAMEPERIODLASTYEAR(dim_date[Date]),dim_date[Inpast]=True)
     2.         PYTD_GrossProfit = CALCULATE([gross_profit],SAMEPERIODLASTYEAR(dim_date[Date]),dim_date[Inpast]=True)
     3.         PYTD_Quantity = CALCULATE([quantity],SAMEPERIODLASTYEAR(dim_date[Date]),dim_date[Inpast]=True)

       ##### YTD Measures :
    This is aimed at tracking the cumulative value of a metric from the beginning of the current year up to the present date.
    This provides a running total that allows businesses to monitor their progress towards annual goals and compare performance over time.
      1.       YTD_Sales = TOTALYTD([sales],fact_sales[Date_Time])
      2.       YTD_GrossProfit = TOTALYTD([gross_profit],fact_sales[Date_Time])  
      3.       YTD_Quantity = TOTALYTD([quantity],fact_sales[Date_Time])
  
3. ### Data Cleaning and Transformation:
   Power Query Editor was used to clean the data and also to transform the data. Few of the data cleaning tasks include;
   
    1. Correcting the data types
    2. Removing and replacing null values
    3. Removing duplicates from the dimension tables

4. ### Date Table creation:

   Creating a Date Table in Power BI is essential for effective time-based analysis and accurate reporting. Here are the key reasons for creating a Date Table:

      1. Time Intelligence Functions
Power BI's built-in time intelligence functions (e.g., YTD, QTD, MTD, SAMEPERIODLASTYEAR) require a well-structured Date Table. These functions enable complex time-based calculations and comparisons, such as:

      - Year-over-Year (YoY) growth
      - Year-to-Date (YTD) calculations
      - Month-to-Date (MTD) and Quarter-to-Date (QTD) calculations
      2. Consistent Date Filtering
A Date Table ensures consistent and accurate filtering and grouping of date-related data across all reports and visuals. It provides a single source of truth for date information, which helps in:
      - Ensuring all visuals use the same date logic
      - Avoiding discrepancies caused by different date formats or granularities
      3. Hierarchical Date Structures
A Date Table allows for the creation of date hierarchies (e.g., Year -> Quarter -> Month -> Day), which are essential for drill-down and drill-up capabilities in Power BI reports. This enables users to explore data at different levels of detail.

      4. Handling Missing Dates
In datasets where dates might be missing, a Date Table ensures continuity by including all dates within the specified range. This is crucial for accurate time series analysis and for avoiding gaps in the data.

      5. Advanced Date Filtering
A Date Table allows for advanced date filtering options, such as:

      - Filtering by fiscal year, quarter, or month
      - Custom date ranges
      - Working with holidays and weekends

5.  ### Slicers:
The slicers created inlude the year and a switch slicer which consists of the Sales, Gross Profit and Quantity.

This is aimed at nmaking the report dynamic and it saves time and efficiency as the performance metrics can be checked either based on sales, gross profit or quantity.
Instead of having to create a different report for sales, gross profit or quantity individuall, this report brings it all together.

6.  ### Visuals:
- Combo chart(Stacked Column chart and Line chart) : This shows the monthly breakdown of the YTD value based on the product type.
  This is then checked agsinst the Gross profit.
    
- Donut chart: YTD by Product size.
   
 - Waterfall chart: This shows the breakdown of the PYTD vs YTD (difference between the YTD & PYTD value) by month and category.
    
- Treemap: Top 10 Countries by PYTD vs YTD value.
     
- Scatter chart: %Gross profit against the YTD with respect to the account.
    
- Treemap: Bottom 10 Countries by PYTD vs YTD value.
   
  


    








   
      
  
