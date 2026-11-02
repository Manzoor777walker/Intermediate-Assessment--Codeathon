# Intermediate-Assessment--Codeathon
This dataset named SalesData_1000Rows_WithIssues.csv which contains customer order information. The dataset has missing values, duplicate entries, and inconsistent date formats.
## Data Cleaning and Loading
             *Import the dataset into Power BI using Power Query Editor.
             *Perform the necessary data cleaning steps to prepare it for analysis, including:
                           i) Handling missing values in columns.
                           ii) Removing duplicate rows.
                           iii) Standardizing the OrderDate column to a consistent date format
             *Load the cleaned dataset into the Power BI model
## Visualizations and Insights
*Using the cleaned dataset, create meaningful visual representations to analyze order and profit trends*
       #*Pie Chart showing order distribution across different regions
       #*Column Chart to display the top 5 trending products based on the number of times each product was ordered
       #*Create a Line Chart to show the profit trend over time.
## DAX Calculations
*Apply DAX to create calculated elements and gain deeper insights*
             **Create a Calculated Table named EastRegionOrders that filters and displays only the orders from the East region.
                    Formula used :EastRegionOrders = FILTER(SalesData,SalesData[Region]="East")
             **Create a Calculated Column to compute the difference between the Profit and Cost columns. Name it ProfitCostDifference.
                    Formula used :ProfitCostDifference= (SaleData[profit]-saleData[cost])
             **Create a Calculated Measure to find the total profit earned. Name it TotalProfit
                    Formula used :Total Profit = SUM(SalesData[Profit])




