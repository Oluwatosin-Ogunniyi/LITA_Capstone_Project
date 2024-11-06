# LITA_Capstone_Project_Sales_Report

### Project Overview
---
This project aims to take a deep dive into the sales report of Capstone Stores across the regions in Nigeria and ascertain the performance drivers for the revenue figures. The insights generated will help the management understand her business dynamics and make strategic business decisions.

### Data Sources
The source of data used for the analysis is SalesData.xls which was spooled from the database of the enterprise business application.

### Tools used
---
- Microsoft excel was used for:
  1. Cleaning the data
  2. Sorting and filtering the data using the pivot table
  3. Analysing the data
  4. Data visualisation
 
- Microsoft SQL Server Management Studio (Structured Query Language) was used for querying the data using both basic and advanced sql languages 
  
- Microsoft PowerBi was used to:
  1. Transform the data
  2. Elinminate columns with null values
  3. Load data
  4. Create visualisation report
  5. Publish report
 
### Data Cleaning
The first step carried out in analysing the sales report was to clean the data, transform the data and format the data to fit for purpose. 

### Exploratory Data Analysis
In exploring the data set for Capstone stores, data analysis was conducted to address the following area of concern:
- The number of sales transactions in each region.
- The highest-selling product by total sales value.
- Total revenue per product.
- The monthly sales totals for the current year.
- The top 5 customers by total purchase amount.

### Data Analysis
---
Microsoft Excel
- While cleaning and filtering the data on Excel, the following formular and commands were used to determine the year and month of transaction from the order date column:
```excel
=Year()
```

```excel
=Month()
```

SQL
- The initial step taken was to create a database for Capstone Sales data and the file was imported from excel for further query. Some of the query languages used were:

**To call up the SalesData table**
```sql
SELECT * FROM SalesData$
```

**Total sales for each product category**
```sql
SELECT Product,SUM(Quantity) AS Total_Quantity_Sold
FROM SalesData$
GROUP BY (Product);
```

**Number of sales transaction in each region**
```sql
SELECT Region, COUNT(Sales) AS Number_of_Sales
FROM SalesData$
GROUP BY (Region);
```
**Total revenue by product**
```sql
SELECT Product,SUM(Sales) AS TOTAL
FROM SalesData$
GROUP BY (Product);
```

**Top 5 customers**
```sql
SELECT Top (5) [Customer Id],Sum(Sales) AS Top_5_Customers
FROM SalesData$
GROUP BY([Customer Id])
ORDER BY Sum(Sales) desc
```
**Higest selling product by total sales**
```sql
SELECT Top (1) Product,Sum(Sales) AS Highest_Selling_Product
FROM SalesData$
GROUP BY(Product)
ORDER BY Sum(Sales) desc
```
### Data Visualization
This is the visual presentation of the diferent charts that depicts the findings from the analysis carried out on Capstone stores sales report across the country.

![Power Bi Dashboard](https://github.com/user-attachments/assets/37e23b9a-950b-4c60-a434-7d303efe40b1)

### Findings and recommendation
