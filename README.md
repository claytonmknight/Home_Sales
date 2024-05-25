# Home_Sales
 Home_Sales
# README

## Runtime Comparison
The runtime of the query calculating the average price of a home per "view" rating was significantly reduced when using cached data compared to uncached data. Additionally, the runtime was comparable when using Parquet DataFrame, indicating efficient data storage and processing.

- Uncached Runtime for Query 6: 1.008 seconds
- Cached Runtime for Query 6: 0.664 seconds
- Parquet DataFrame Runtime for Query 6: 0.994 seconds

### Note:
The provided starter code stated to use spark-3.4.0, but spark 3.4.3 was used instead.

## Google Colab
This project was completed using Google Colab.

## Description
This script performs various data analysis tasks using Apache Spark SQL on a dataset of home sales. It accomplishes the following tasks:

- Reads a CSV file containing home sales data from an AWS S3 bucket.
- Creates a temporary view of the DataFrame for further analysis.
- Calculates the average price for a four-bedroom house sold per year, rounded to two decimal places.
- Calculates the average price of a home for each year the home was built, having 3 bedrooms and 3 bathrooms, rounded to two decimal places.
- Calculates the average price of a home for each year the home was built, having 3 bedrooms, 3 bathrooms, with two floors, and are greater than or equal to 2,000 square feet, rounded to two decimal places.
- Determines the average price of a home per "view" rating, rounded to two decimal places, having an average home price greater than or equal to $350,000, and orders by descending view rating. Measures the runtime for this query.
- Caches the temporary table home_sales.
- Checks if the table home_sales is cached.
- Using the cached data, runs the query from step 6, calculating the average price of a home per "view" rating, rounded to two decimal places, having an average home price greater than or equal to $350,000. Determines the runtime and compares it to the uncached runtime.
- Partitions the home sales data by the "date_built" field and writes it to Parquet format.
- Reads the Parquet formatted data.
- Creates a temporary table for the Parquet data.
- Using the Parquet DataFrame, runs the query from step 6, calculating the average price of a home per "view" rating, rounded to two decimal places, having an average home price greater than or equal to $350,000. Determines the runtime and compares it to the cached runtime.
- Uncaches the temporary table home_sales.
- Checks if the table home_sales is no longer cached.

## Answers to Queries
Query 3:
Average Price for a Four-Bedroom House Sold Per Year (rounded to two decimal places):

- 2019: $300,263.70
- 2020: $298,353.78
- 2021: $301,819.44
- 2022: $296,363.88

Query 4:
Average Price of a Home for Each Year Built with 3 Bedrooms and 3 Bathrooms (rounded to two decimal places):

- 2010: $292,859.62
- 2011: $291,117.47
- 2012: $293,683.19
- 2013: $295,962.27
- 2014: $290,852.27
- 2015: $288,770.30
- 2016: $290,555.07
- 2017: $292,676.79

Query 5:
Average Price of a Home for Each Year Built with 3 Bedrooms, 3 Bathrooms, Two Floors, and Area ≥ 2,000 sqft (rounded to two decimal places):

- 2010: $285,010.22
- 2011: $276,553.81
- 2012: $307,539.97
- 2013: $303,676.79
- 2014: $298,264.72
- 2015: $297,609.97
- 2016: $293,965.10
- 2017: $280,317.58

Query 6:
Average Price of a Home per "View" Rating (rounded to two decimal places) with Average Price ≥ $350,000 (ordered by descending view rating):

- View 100: $1,026,669.50
- View 99: $1,061,201.42
- View 98: $1,053,739.33
- View 97: $1,129,040.15
- View 96: $1,017,815.92
- View 95: $1,054,325.60
- View 94: $1,033,536.20
- View 93: $1,026,006.06
- View 92: $970,402.55
- View 91: $1,137,372.73
- View 90: $1,062,654.16
- View 89: $1,107,839.15
- View 88: $1,031,719.35
- View 87: $1,072,285.20
- View 86: $1,070,444.25
- View 85: $1,056,336.74
- View 84: $1,117,233.13
- View 83: $1,033,965.93
- View 82: $1,063,498.00
- View 81: $1,053,472.79