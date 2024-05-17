# Coffee Shop Exploratory Analysis |  2024-04-12

> [!NOTE]
> For better visual, download the HTML file included in respiratory.

## Contents of Table
- Data Background
- Objectives
- Enviroment Setup
  - Connecting to database
  - Extracting Data
  - Data Cleaning
  - Missing Values
  - Feature Creation
- Exploratory Analysis
  - Univariate Analysis
     - Summary Statistics
     - Distributions
  - Bivariate & Multivariate Analysis
     - Numerical Variables Relationship
     - Sales Performance
     - Sales Performance By Location
     - Sales Performance By Category, Product, and Size
- Conclusion

$~$

# Data Background
The dataset comprises transactional records from Maven Roasters, a fictional NYC-based coffee shop operating across three distinct locations. It encompasses comprehensive details such as transaction dates, timestamps, geographical specifics, and product-level information.

Based on the dataset information, these are the columns and their description:
| Field | Type | Descriptions |
| --- | --- | --- |
| transaction_id | Numeric | Unique identifier for each transaction. |
| transaction_date | Date | Date when the transaction occurred. |
| transaction_time | Time	| Time of the transaction. |
| transaction_qty	| Numeric	| Quantity of products purchased in a transaction. |
| store_id	| Numeric | Unique identifier for each store location. |
| store_location	| Text	| Name or description of the store’s physical location. |
| product_id	| Numeric	| Unique identifier for each product sold. |
| unit_price	| Numeric	| Price of a single unit of the product in the transaction. |
| product_category	| Text	| General category to which the product belongs (e.g., Coffee, Tea, Drinking Chocolate). |
| product_type	| Text	| Specific type or variant of the product (e.g., Gourmet brewed coffee, Brewed Chai tea, Hot chocolate). |
| product_detail	| Text	| Additional details about the product(e.g., specific flavor, size, or blend) |

$~$

# Objectives
Our primary goal in this analysis is to understand the data and generate valuable insights for future decision-making. We will explore the data as much as possible. We can achieve our primary goal by performing the following:

1.) Identify the data structure: Through exploratory analysis, we can recognize the various data types that are present, how they are distributed, and the general structure of the data.

2.) Ensure data quality: We will evaluate the reliability and quality of the data by detecting anomalies and outliers in the dataset, addressing missing values, and correcting data type errors.

2.) Identify patterns and relationships: Analyze the dataset’s pattern and the relationship between its columns by examining it and applying different techniques to find hidden patterns.

$~$

# Enviroment Setup
```r
library(tidyverse) # General
library(lubridate) # Date Converter
library(tidycomm)  # Statistical Summary
library(scales)    # Numerical Labelling
library(e1071)     # Skew Scalling / Class Analysis
library(reshape2)  # Restructure and Aggregate Data
 
library(ggplot2)   # Data Visualization
library(ggthemes)  # Data Visual Theme
library(patchwork) # Combining Visuals

library(RPostgres) # PostgreSQL Database

 # General Color
 color = '#2879D8'
  
 # General Theme
 theme_set(theme_fivethirtyeight())
```



