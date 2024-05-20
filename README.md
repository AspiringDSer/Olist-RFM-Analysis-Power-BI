# Olist - RFM Analysis - Power BI

# Table of Content

1. [Project Overview](#Project-Overview)
2. [Data Sources](#Data-Sources)
3. [Data Model](#Data-Model)
4. [Report Structure](#Report-Structure)
5. [RFM Calculation](#RFM-Calculation)
6. [RFM Segmentation](#RFM-Segmentation)
7. [Future Developments](#Future-Developments)

<a name='Project-Overview'></a>
# Project Overview
[Go to TOC](#top)

| Skills Demonstrated                  |             |                             |
| ------------------------------------ | ----------- | --------------------------- |
| Customer Segmentation (RFM Analysis) | Power BI    | Data Modeling (Star Schema) |
| DAX                                  | Power Query | Python                      |

![RFM Overview](https://github.com/AspiringDSer/Olist-RFM-Analysis-Power-BI/assets/79289892/6bdddbaf-c04c-4643-a745-5a46806713d0)

## Objective 

The objective of this project is to perform an RFM (Recency, Frequency, Monetary) Analysis on an E-Commerce Dataset to segment customers based on their purchasing behavior and provide actionable insights for targeted marketing strategies.
## Methodology Overview 

The RFM model categorizes customers based on:

![RFM Metrics](https://github.com/AspiringDSer/Olist-RFM-Analysis-Power-BI/assets/79289892/cc6654f5-537f-4d0b-a216-3cfd6cf32abb)

Customers are scored on each of these dimensions, and combined scores are used for segmentation.
## Key Features

- **Data Cleansing and Transformation**: 
	- **Handling Missing Values:** Employed various techniques to manage missing data. Where necessary, records with excessive missing data were removed to ensure data quality.
	- **Outlier Detection and Treatment:** Identified outliers using statistical methods such as the IQR (Interquartile Range) method.. Removed outliers that fall outside the +/- 5% boundaries to maintain data integrity.
	- **Feature Engineering:** Created new features from existing data to enhance the predictive power of the RFM model, such as calculating the days since the last purchase for the recency score.
	
	More details can be found in the [Jupyter Notebook](https://github.com/AspiringDSer/Olist-RFM-Analysis-Power-BI/blob/master/Olist%20-%20RFM%20Analysis.ipynb). 
	
- **Calculation of RFM Scores for Each Customer**

![RFM Scores](https://github.com/AspiringDSer/Olist-RFM-Analysis-Power-BI/assets/79289892/c417a147-edf4-4899-a382-6869d100c09e)

- **Visualization of Segments and Insights**

![Customer Segmentation](https://github.com/AspiringDSer/Olist-RFM-Analysis-Power-BI/assets/79289892/525a4ccf-8264-402d-8ef0-a2b203f18a3f)

<a name='Data-Sources'></a>
# Data Sources
[Go to TOC](#top)

The project's visualizations and analyses are based on the E-Commerce Dataset by Olist. This is a Brazilian ecommerce public dataset of orders made at [Olist Store](https://olist.com/pt-br/). The dataset has information of 100k orders from 2016 to 2018 made at multiple marketplaces in Brazil. Its features allows viewing an order from multiple dimensions: from order status, price, payment and freight performance to customer location, product attributes and finally reviews written by customers. 

**Context**
**[Olist](https://olist.com/pt-br/)** is a **Brazilian** departmental store (_marketplace_) that operates in e-commerce segment. It connects small businesses from all over Brazil to channels without hassle and with a single contract. Those merchants are able to sell their products through the Olist Store and ship them directly to the customers using Olist logistics partners.

**Data Processing:**

- **Source Data:** The dataset originates from the [Kaggle website](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce) in CSV format.
- **Data Cleansing and Transformation**: Detailed steps can be found in the [Jupyter Notebook](https://github.com/AspiringDSer/Olist-RFM-Analysis-Power-BI/blob/master/Olist%20-%20RFM%20Analysis.ipynb). 
- **Integration with Power BI:** The processed data were subsequently loaded into Power BI.

<a name='Data-Model'></a>
# Data Model
[Go to TOC](#top)

![Data Model](https://github.com/AspiringDSer/Olist-RFM-Analysis-Power-BI/assets/79289892/fa79e0e7-c57e-416a-9089-d751d123de28)
The project utilized **Dimensional Data Modeling** to structure the E-commerce dataset, employing the **star schema** to construct both Fact and Dimension Tables. This approach allows for efficient data storage and retrieval, enabling users to analyze the data from different perspectives easily.

| CSV File                         | Table Description                                                                                                                                                                                               |
| -------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| olist_orders_dataset.csv         | This table contains order level facts related to the dataset, such as Order ID and Order Date.                                                                                                                  |
| olist_order_payments_dataset.csv | This table contains payment details related to the datasets, such as Payment Type and Payment Value.                                                                                                            |
| olist_customers_dataset.csv      | This table contains information about the customer and its location.                                                                                                                                            |
| segmentation_overview.csv        | This table provides a detailed breakdown of customer segments based on their RFM scores, along with a hierarchical grouping into broader categories.                                                            |
| segmentation_recommendations.csv | This table serves as a key component of the RFM analysis, providing a structured summary of customer segmentation and corresponding retention strategies.                                                       |
| glossary.csv                     | This glossary serves as a reference tool for individuals reviewing the RFM analysis, particularly those who may not be familiar with the specific terminology used in data analytics and customer segmentation. |

<a name='Report-Structure'></a>
# Report Structure
[Go to TOC](#top)

The Power BI dashboard is structured to provide users with interactive and insightful analysis of the E-commerce dataset. It allows navigation between seven pages and one glossary, each focusing on different aspects of the data:

1. **RFM Overview**: This page provides a summary of the Recency, Frequency, and Monetary analysis. It includes visualizations and metrics that give an at-a-glance understanding of the overall customer segmentation based on their RFM scores.
   
![RFM Overview](https://github.com/AspiringDSer/Olist-RFM-Analysis-Power-BI/assets/79289892/a6fc1df9-e6ed-4dd3-bcf7-2008e3efe8c2)
 
2. **RFM Movement**: This page tracks the changes in customer segments over time. It helps identify trends and shifts in customer behavior, showing how customers move between different RFM segments.

![RFM Movement](https://github.com/AspiringDSer/Olist-RFM-Analysis-Power-BI/assets/79289892/5f4dd957-b16e-455f-aa2e-5800ddcbc88f)
    
3. **RFM Cohorts**: This page analyzes customer cohorts based on their RFM scores. It focuses on the behavior and performance of different customer groups over specific time periods, aiding in cohort-based analysis and comparison.

![RFM Cohorts](https://github.com/AspiringDSer/Olist-RFM-Analysis-Power-BI/assets/79289892/c6f0f5b5-4b91-4b4e-94af-6a5e74e46af9)

4. **Recency Analysis**: This page delves into the recency aspect of the RFM analysis. It includes detailed metrics and visualizations that show how recently customers have made purchases, highlighting trends in customer engagement.

![Recency Analysis](https://github.com/AspiringDSer/Olist-RFM-Analysis-Power-BI/assets/79289892/1c7490f5-e822-42ac-bd91-b98f88542b0a)

5. **Frequency Analysis**: This page focuses on the frequency of customer purchases. It provides insights into how often customers are buying, helping to identify loyal customers who purchase frequently.

![Frequency Analysis](https://github.com/AspiringDSer/Olist-RFM-Analysis-Power-BI/assets/79289892/0d998536-b6f2-45db-81a4-f23a3e4e97c0)

6. **Monetary Analysis**: This page examines the monetary value of customer purchases. It includes detailed analyses and visualizations of the total spending by customers, identifying high-value customers who contribute significantly to revenue.

![Monetary Analysis](https://github.com/AspiringDSer/Olist-RFM-Analysis-Power-BI/assets/79289892/f82bc3ec-32be-423c-a9d4-dfbc820727b4)

7. **Recommendations**: This page offers actionable insights and strategic recommendations based on the RFM analysis. It provides guidance on how to target different customer segments to improve retention and maximize profitability.

![Recommendations](https://github.com/AspiringDSer/Olist-RFM-Analysis-Power-BI/assets/79289892/6c0c9a90-7320-4931-821b-babc547f22bb)
    
8. **Glossary**: This page includes definitions of key terms and concepts used in the RFM analysis. It serves as a reference tool to ensure clarity and understanding of specialized terminology used throughout the dashboard.

![Glossary](https://github.com/AspiringDSer/Olist-RFM-Analysis-Power-BI/assets/79289892/68e97757-629e-4eb4-9e38-927fda516611)

<a name='RFM-Calculation'></a>
# RFM Calculation
[Go to TOC](#top)
## Introduction to RFM Analysis
RFM Analysis is a powerful marketing technique used to segment customers based on their purchasing behavior. The acronym RFM stands for Recency, Frequency, and Monetary value, each representing a key metric that helps businesses understand customer engagement and value.

- **Recency (R):** This metric measures how recently a customer made their last purchase. Customers who have made a purchase more recently are considered more engaged and are likely to respond positively to new marketing efforts.
    
- **Frequency (F):** This metric measures how often a customer makes a purchase within a given time period. Customers with higher purchase frequencies are considered more loyal and valuable to the business.
    
- **Monetary (M):** This metric measures the total amount of money a customer has spent during a specific period. Customers who spend more are often more valuable and should be treated with special attention.

By scoring each customer on these three metrics, businesses can create distinct customer segments and tailor marketing strategies accordingly. For example, customers with high recency, frequency, and monetary scores are the most valuable and may be targeted with special promotions or loyalty programs. Conversely, customers with low scores across these metrics might need re-engagement campaigns to revive their interest in the brand.

## Recency Calculation
**Recency (R):** This metric measures how recently a customer made their last purchase. Customers who have made a purchase more recently are considered more engaged and are likely to respond positively to new marketing efforts.

**Calculation Method:** Number of days since the last transaction (purchase).

**Code Snippet:** 

![recency_code_snippet](https://github.com/AspiringDSer/Olist-RFM-Analysis-Power-BI/assets/79289892/30971a5f-e69f-4d41-b1c0-92b58b21ded9)

More details can be found in the [Jupyter Notebook](https://github.com/AspiringDSer/Olist-RFM-Analysis-Power-BI/blob/master/Olist%20-%20RFM%20Analysis.ipynb). 

## Frequency Calculation
**Frequency (F):** This metric measures how often a customer makes a purchase within a given time period. Customers with higher purchase frequencies are considered more loyal and valuable to the business.

**Calculation Method:** Number of orders.

**Code Snippet:**

![frequency_code_snippet](https://github.com/AspiringDSer/Olist-RFM-Analysis-Power-BI/assets/79289892/31d18727-deca-4abe-86d6-a67f09e0828b)

More details can be found in the [Jupyter Notebook](https://github.com/AspiringDSer/Olist-RFM-Analysis-Power-BI/blob/master/Olist%20-%20RFM%20Analysis.ipynb). 

## Monetary Calculation
**Monetary (M):** This metric measures the total amount of money a customer has spent during a specific period. Customers who spend more are often more valuable and should be treated with special attention.

**Calculation Method:** The sum of total spend per customer. 

**Code Snippet:**

![monetary_code_snippet](https://github.com/AspiringDSer/Olist-RFM-Analysis-Power-BI/assets/79289892/6ca55db8-06c0-4951-913f-e4b2bcff9b53)

More details can be found in the [Jupyter Notebook](https://github.com/AspiringDSer/Olist-RFM-Analysis-Power-BI/blob/master/Olist%20-%20RFM%20Analysis.ipynb). 

## RFM Score Aggregation
Once we have calculated the Recency, Frequency, and Monetary values for each customer, the next step is to assign scores to these values and combine them into a composite RFM score. This process helps in categorizing customers based on their purchasing behavior.

### Step-by-Step Process

1. **Assigning RFM Scores:**
    
    - **Recency Score (R):** Customers are divided into quintiles based on recency. The most recent purchasers receive the highest score (1), and the least recent receive the lowest score (5).
    - **Frequency Score (F):** Customers are divided into quintiles based on frequency. The most frequent purchasers receive the highest score (5), and the least frequent receive the lowest score (1).
    - **Monetary Score (M):** Customers are divided into quintiles based on monetary value. The highest spenders receive the highest score (5), and the lowest spenders receive the lowest score (1).

**Combining Scores:** Each customer’s RFM score is a concatenation of their individual Recency, Frequency, and Monetary scores, resulting in a three-digit score. For example, a customer with an R score of 4, an F score of 3, and an M score of 5 would have an RFM score of 435.

**Code Snippet:** 

![RFM Scores Calculation](https://github.com/AspiringDSer/Olist-RFM-Analysis-Power-BI/assets/79289892/c72977ff-879c-4bee-a1dd-3ed4db072bea)

More details can be found in the [Jupyter Notebook](https://github.com/AspiringDSer/Olist-RFM-Analysis-Power-BI/blob/master/Olist%20-%20RFM%20Analysis.ipynb). 

<a name='RFM-Segmentation'></a>
# RFM Segmentation
[Go to TOC](#top)

## Explanation of the Scoring System
The RFM scoring system is designed to segment customers based on their purchasing behavior. By assigning scores to each customer's Recency, Frequency, and Monetary values, we can categorize customers into distinct segments, allowing for targeted marketing and personalized engagement strategies.

### Scoring Methodology

1. **Recency (R) Score:**
    
    - Customers are divided into quintiles based on the recency of their last purchase.
    - The most recent purchasers receive the highest score (1), while the least recent receive the lowest score (5).
    
1. **Frequency (F) Score:**
    
    - Customers are divided into quintiles based on the frequency of their purchases.
    - The most frequent purchasers receive the highest score (5), while the least frequent receive the lowest score (1).
    
1. **Monetary (M) Score:**
    
    - Customers are divided into quintiles based on their total monetary spend.
    - The highest spenders receive the highest score (5), while the lowest spenders receive the lowest score (1).

### Combined RFM Score
Each customer's RFM score is a three-digit number formed by concatenating their individual Recency, Frequency, and Monetary scores. For example, a customer with an R score of 4, an F score of 3, and an M score of 5 would have an RFM score of 435.

### Customer Segments
Based on the combined RFM scores, we can classify customers into the following segments:

![Scoring System](https://github.com/AspiringDSer/Olist-RFM-Analysis-Power-BI/assets/79289892/9b861047-5ba9-4fff-b8cc-749376b6ceb8)

[Source](https://documentation.bloomreach.com/engagement/docs/rfm-segmentation)

By utilizing this scoring system, we can create tailored marketing campaigns that address the specific needs and behaviors of each customer segment, ultimately driving higher engagement, loyalty, and revenue.

<a name='Future-Developments'></a>
# Future-Developments
[Go to TOC](#top)

To further enhance this project, I plan to implement several key improvements:

1. **Cloud-Based Data Warehouse Solution:**
    
    - **Objective:** Create a cloud-based data warehouse to optimize data storage and management.
    - **Approach:** Use Dimensional Data Modeling principles to design and deploy the dataset into the cloud-based solution. This will not only streamline data management but also enhance scalability and accessibility, making it easier to handle growing data volumes and provide real-time analytics.
    
2. **Machine Learning Integration:**
    
    - **Objective:** Deploy a K-means clustering model to complement the RFM analysis.
    - **Approach:** Implement a K-means clustering algorithm to further segment customers based on their RFM scores. This will provide more granular insights into customer behavior, enabling more targeted marketing strategies and personalized customer experiences.

These enhancements aim to elevate the project's capabilities, making it a more robust and comprehensive tool for data analysis and customer segmentation.
