# Power_BI_Projects
# Sales Analysis Dashboard

## Overview
This Power BI project analyzes sales performance based on different product categories, providing key insights into revenue trends and customer behavior.

## Data Source
- (https://www.kaggle.com/datasets/logiccraftbyhimanshi/walmart-customer-purchase-behavior-dataset)

## Key Insights
- **Top Performing product Categories**: Products from Beauty Catgeory had the highest revenue.
- 
- **Sales Trends**: Total sales trended up, resulting in a 4.42% increase between Thursday, February 29, 2024 and Friday, January 24, 2025.﻿
- **Customer Segmentation**: Majority of sales from returning customers. Most of the sales from customers in the age of late 30's


## Visualizations
- Pie charts for catgeory wise sales
- Line charts for quarterly trends - Category wise
- Heatmaps for regional sales
- Bar Graph for sale based on age

## Technologies Used
- Power BI
- DAX for calculated measures
- Python for identifying anamolies using z score

  # #code data cleaning (python)

  #data cleaning for Sales purchase records
import pandas as pd
df = pd.read_csv("D:\important documents\Sales purchase data.csv")
df.head()   # Displays no. of rows
df.info()   # Shows data types and missing values
df.describe()  # Summary statistics

#identifying outlier:

OTcolumn = "Purchase_Amount"

from scipy import stats

#Compute Z-score for a numeric column
df["z_score"] = stats.zscore(df[OTcolumn])

#Identify outliers
outliers = df[(df["z_score"] > 3) | (df["z_score"] < -3)]
print(outliers)

## this project is a sample and does not represent actual data of any organisation


## How to Use
Download the `.pbix` file and open it in Power BI Desktop.
