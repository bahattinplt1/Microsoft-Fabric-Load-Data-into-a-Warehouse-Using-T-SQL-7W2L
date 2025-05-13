# Microsoft Fabric: Load Data into a Warehouse Using T-SQL

This project demonstrates how to build and load a data warehouse using Microsoft Fabric, starting from ingesting raw data into a lakehouse and ending with analytical queries. The steps were followed based on the Microsoft Learn lab ["Load data into a warehouse using T-SQL"](https://microsoftlearning.github.io/mslearn-fabric/Instructions/Labs/06a-data-warehouse-load.html?azure-portal=true).

## Prerequisites

- Microsoft Fabric trial or enabled capacity
- Basic familiarity with T-SQL and Power BI interface

## Overview of Steps

1. **Create a Workspace**: Set up a new Fabric-enabled workspace at [fabric.microsoft.com](https://app.fabric.microsoft.com).

2. **Create a Lakehouse and Upload File**: 
   - Create a lakehouse.
   - Download the sample CSV file from:
     ```
     https://github.com/MicrosoftLearning/dp-data/raw/main/sales.csv
     ```
   - Upload it to the Files section of the lakehouse.

3. **Create Table in Lakehouse**: Use the "Load to tables" option on the `sales.csv` file to create a table named `staging_sales`.

4. **Create a Warehouse**: From the workspace, create a new Data Warehouse.

5. **Create Tables and Schema**: In the SQL editor, define:
   - `Sales.Fact_Sales`
   - `Sales.Dim_Customer`
   - `Sales.Dim_Item`

6. **Create View for Staging Table**: Reference the `staging_sales` table from the lakehouse via a SQL view called `Sales.Staging_Sales`.

7. **Load Data Using Stored Procedure**: Create and execute a procedure `Sales.LoadDataFromStaging` to load 2021 data from the view into the warehouse.

8. **Run Analytical Queries**:
   - Total sales per customer
   - Top-selling items
   - Top customer per category (Bike, Helmet, Gloves)

## Screenshot

The full process is illustrated below:

Screenshot

## Result Highlights

- **Jordan Turner** was the top customer by sales in 2021.
- **Mountain-200** bikes were the top-selling products.
- Categorized queries identified top customers per product category.

## License

This project is based on Microsoft Learn materials and is for educational purposes only.
