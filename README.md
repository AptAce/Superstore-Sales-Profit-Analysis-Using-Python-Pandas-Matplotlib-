# Superstore-Sales-Profit-Analysis-Using-Python-Pandas-Matplotlib-
This project presents a comprehensive exploratory data analysis (EDA) of a Superstore dataset using Python.
**Introduction**
This project presents an exploratory data analysis (EDA) of a Superstore dataset containing 51,290 rows and 27 columns. The objective of this project was to analyze sales performance, profitability, discount patterns, product movement, and time-based trends by answering 20 structured business questions.

Using Pandas for data manipulation and Matplotlib for visualization, the dataset was explored to extract actionable insights regarding:

Sales performance across categories and regions

Profit distribution

Quantity movement

Discount patterns

Yearly and monthly sales trends

The goal of this project was not only to compute numerical results but also to interpret them from a business perspective.

**🛠 Tools & Libraries Used**

Python

Pandas

Matplotlib

**Methodology / Procedure**
**A. Data Importation**

The dataset was imported using:

import pandas as pd
Df = pd.read_csv("superstore.csv")

**B. Dataset Overview & Cleaning**
 **1. Dataset Shape**
Df.shape


Result: 51,290 rows and 27 columns

 **2. Numerical Columns Identification**
Df.select_dtypes(include=['int64', 'float64'])


This identified all columns containing numerical data.

 **3. Missing Values Check**
Df.isnull().sum()


Result: No significant missing values detected.

 **4. Duplicate Rows Check**
Df.duplicated().sum()


Result: 0 duplicate rows found in the dataset.

**C. Sales Analysis**
 **5. Total Sales**
Df['Sales'].sum()


Total Sales: 12,642,905

 **6. Highest Selling Category**

Grouped by category and summed sales:

Df.groupby('Category')['Sales'].sum()


Result: Technology recorded the highest total sales.

 **7. Sub-Category with Lowest Sales**
Df.groupby('Sub.Category')['Sales'].sum()


This identified the lowest-performing sub-category in terms of sales.

 **8. Average Sales Per Order**
Df['Sales'].mean()


This calculated the average revenue generated per order.

 **9. Sales by Region**
Df.groupby('Region')['Sales'].sum()


This showed how total sales vary across different regions.

**D. Profit Analysis**
 **10. Total Profit**
Df['Profit'].sum()


This computed overall profitability.

 **11. Most Profitable Region**
Df.groupby('Region')['Profit'].sum()


Identified the region generating the highest total profit.

 **12. Most Profitable Category**
Df.groupby('Category')['Profit'].sum()


Determined which category contributed the most to total profit.

 **13. Sub-Category with Lowest Average Profit**
Df.groupby('Sub.Category')['Profit'].mean()


This revealed the weakest performing sub-category on average profit basis.

**E. Quantity Analysis**
 **14. Total Quantity Sold**
Df['Quantity'].sum()


This calculated total units sold across all transactions.

 **15. Category with Highest Quantity Sold**
Df.groupby('Category')['Quantity'].sum()


Identified the category with the highest product movement.

**F. Discount Analysis**
 **16. Average Discount Across Orders**
Df['Discount'].mean()


Calculated the overall discount rate given to customers.

 **17. Region with Highest Average Discount**
Df.groupby('Region')['Discount'].mean()


Identified which region offers the highest average discount.

**G. Time Series Analysis**

The Order.Date column was converted to datetime format:

Df['Order.Date'] = pd.to_datetime(Df['Order.Date'])

 **18. Yearly Sales Trend**
sales_by_year = Df.groupby(Df['Order.Date'].dt.year)['Sales'].sum()


Yearly Sales:

2011: 2,259,511

2012: 2,677,493

2013: 3,405,860

2014: 4,300,041

A line chart was plotted to visualize the trend.

 **19. Month with Highest Sales**
Df['Month'] = Df['Order.Date'].dt.month_name()
Df.groupby('Month')['Sales'].sum()


This identified the month that recorded the highest total sales.

**H. Key Findings & Results**
 1. Strong Upward Sales Growth

Sales increased consistently from 2011 to 2014, showing a clear upward trend.
There was no decline or fluctuation, indicating steady business expansion.

 2. Technology Dominates Sales

The Technology category generated the highest total sales, indicating strong customer demand in that segment.

 3. Regional Differences in Performance

Sales, profit, and discount levels varied across regions, suggesting differences in pricing strategy and market strength.

 4. Product Movement Insights

Some categories sell high volumes but may not necessarily generate the highest profit, indicating margin differences.

 5. Discount Strategy Impact

Regions offering higher average discounts may influence profitability, highlighting potential pricing optimization opportunities.

 **Business Interpretation**

The Superstore dataset demonstrates consistent growth over the four-year period analyzed. The steady upward trend in yearly sales suggests effective sales strategies, increasing customer demand, and business expansion.

While certain categories such as Technology dominate in sales performance, variations in regional discount strategies and sub-category profitability indicate areas where strategic adjustments could improve overall profitability.

**Conclusion**

This project demonstrates practical data analysis skills using Python, including:

Data exploration and cleaning

Grouping and aggregation

Time-series analysis

Business insight generation

Data visualization

By transforming raw transactional data into meaningful insights, this analysis highlights how data-driven decision-making can support business growth and strategic optimization.
