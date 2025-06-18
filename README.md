📱 Mobile Sales Dashboard – Power BI Project

📌 Project Overview
This Power BI dashboard provides an interactive analytical overview of mobile phone sales data across various cities in India. It enables stakeholders to monitor sales trends, understand customer preferences, and identify top-performing models and regions. Key insights such as quantity sold, total revenue, product ratings, and preferred payment methods are visualized to support data-driven decisions.

🎯 Problem Statement
The primary goal of this project is to analyze mobile sales performance using a dynamic dashboard. Retail decision-makers need to understand:
Which cities and brands contribute most to revenue?
What are the sales trends over time?
How do customers rate different products?
Which payment methods are preferred?
Which days of the week show higher sales?
By gaining these insights, companies can enhance marketing strategies, stock management, and customer service.

🛠️ Steps Followed
Data Loading: Imported the sales dataset (CSV) into Power BI Desktop.
Data Cleaning: Used Power Query Editor to:
Rename columns for clarity
Remove unnecessary fields
Format data types correctly (dates, decimals, text)

Modeling: Established a relationship between 'Sales'[Order Date] and the 'Calendar'[Date] column.
DAX Measures:
Total Sales:
DAX
Total Sales = SUM('Sales'[Amount])

Quantity Sold:
DAX
Quantity Sold = SUM('Sales'[Quantity])

Total Orders:
DAX
Total Orders = COUNTROWS('Sales')

Rating Category using IF-ELSE logic:
DAX
Rating Category = 
IF('Sales'[Rating] >= 4, "Good", 
   IF('Sales'[Rating] >= 3, "Average", "Poor"))
   
Time Intelligence Measures:
Month-to-Date Sales:
DAX
MTD Sales = TOTALMTD([Total Sales], 'Calendar'[Date])

Same Period Last Year:
DAX
SPLY Sales = CALCULATE([Total Sales], SAMEPERIODLASTYEAR('Calendar'[Date]))

Visuals Created:
Map Visual – Total Sales by City
Line Chart – Monthly Sales Trend
Bar Chart – Top Selling Models
Pie Chart – Payment Method Distribution
Stacked Bar Chart – Day-wise Sales
Cards – Total Revenue, Quantity Sold, Total Orders
Slicers – Brand, Model, Payment Method, Year-Month

UI Enhancements:
Used built-in themes for styling
Added company logo and header titles
Applied consistent color codes for visuals

Publishing:
Published report to Power BI Service
Verified cross-filtering and responsive behavior

📈 Key Insights
Top Cities: Certain cities consistently contribute to the highest revenue.
Trend Analysis: Noticeable sales spikes during holidays and product launches.
Best-Selling Models: Identified top-performing mobile models by quantity sold.
Customer Ratings:
Most models rated as "Good"
A few low-rated models categorized as "Poor" require attention
Payment Preference:
UPI and Card payments dominate
Cash usage is declining
Sales by Weekday:
Weekends see higher sales volumes compared to weekdays

💡 Learnings
Developed strong understanding of DAX, especially IF-ELSE logic and time intelligence
Learned to build a custom calendar and apply it for accurate trend analysis
Gained hands-on experience in building visually compelling and insight-driven dashboards

