# Intermediate-Assessment--Codeathon
This dataset named SalesData_1000Rows_WithIssues.csv which contains customer order information. The dataset has missing values, duplicate entries, and inconsistent date formats.
## Data Cleaning and Loading
             *Import the dataset into Power BI using Power Query Editor.
             *Perform the necessary data cleaning steps to prepare it for analysis, including:
                           i) Handling missing values in columns.
                           ii) Removing duplicate rows.
                           iii) Standardizing the OrderDate column to a consistent date format
### Procedure
                   •	Remove duplicates on the data set.
                   •	In Date Column check for blank cells and using ETL tool to convert blank rows to null type. Also identified only two rows are blank in date column so convert that column to proper null.
                   •	Customer Name, Region, Category, Product  Columns Setting data types and trim, clean , Proper function has been done. Also convert the blank cells to “Unknown” by using find and replace method.
                   •	On product Column has Blank rows so maintaining data consistency and fill up the blanks, created a calculated column for product based on region.
                          *Using clustered column chart used to find out region based count of product and fill up the blank rows based on that and rename the Column as product, Remove old product column
In Power query editor,Formula used:
                  = if [Product] = "Unknown" and [Region] = "East" then "Monitor"
                  else if [Product] = "Unknown" and [Region] = "South" then   "Headphones"
                  else if [Product] = "Unknown" and [Region] = "West" then "Desk Chair"
                  else if [Product] = "Unknown" and [Region] = "North" then "Bookshelf"
                  else [Product]

                  •	Unit price, Sales, Cost, Profit column has blank rows and  convert them into null.
                  •	By filling blank rows in Sales, Unit price, Cost , Profit column ,Created a calculated column for each column .
                          Formula used;
                                             a.	Sales   : =if [unit price] <>  null then Number.round([Quantity] * [Unit price]) else [sale]
                                             b.	Unit price: = if [sale] <> null then number.round([Sales]/[Quantity]) else [unit price]
                                             c.	Cost: =if [profit]  <> null then number.round ([sales]-[Profit]) else [Cost]
                                             d.	Profit: =if [profit] = null then number.round([Sales]-[Cost]) else [profit]
                  •	Standardizing the OrderDate column to a consistent date format.
                  •	Ensured the data types of all column.


                                 iv)Load the cleaned dataset into the Power BI model
                                 
## Visualizations and Insights
*Using the cleaned dataset, create meaningful visual representations to analyze order and profit trends*
       #*Pie Chart showing order distribution across different regions
       #*Column Chart to display the top 5 trending products based on the number of times each product was ordered
       #*Create a Line Chart to show the profit trend over time.
## DAX Calculations
*Apply DAX to create calculated elements and gain deeper insights*
                    	Create a Calculated Table named EastRegionOrders that filters and displays only the orders from the East region.
                              Formula used :EastRegionOrders =FILTER(SalesDatiis,SalesDatiis[Region]="East")
                    	Create a Calculated Column to compute the difference between the Profit and Cost columns. Name it ProfitCostDifference
                          Formula used as: ProfitCostDifference = (SalesDatiis[Profit]-SalesDatiis[Cost])
                    	Create a Calculated Measure to find the total profit earned. Name it TotalProfit
                          Formula used as:TotalProfit = SUM(SalesDatiis[Profit])
                                                 




