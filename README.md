# Olist - RFM Analysis - Power BI

> [!IMPORTANT]  
> README documentation is currently under construction and will be completed soon. Expected completion date: May 19 2024. Thank you for your patience!

# Table of Content

1. [Project Overview](#Project-Overview)
2. [Data Sources](#Data-Sources)
3. [Data Model](#Data-Model)
4. [Report Structure](#Report-Structure)
5. [RFM Calculation](#RFM-Calculation)
6. [RFM Segmentation](#RFM-Segmentation)
7. [Visualizations and Insights](#Visualizations-and-Insights)
8. [Conclusion and Recommendations](#Conclusion-and-Recommendations)
9. [Challenges and Solutions](#Challenge-and-Solutions)
10. [Visual Samples](#Visual-Samples)
11. [Appendix](#Appendix)
12. [Future Developments](#Future-Developments)

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

![[RFM Metrics.png]]

Customers are scored on each of these dimensions, and combined scores are used for segmentation.
## Key Features

- **Data Cleansing and Transformation**: 
	- **Handling Missing Values:** Employed various techniques to manage missing data. Where necessary, records with excessive missing data were removed to ensure data quality.
	- **Outlier Detection and Treatment:** Identified outliers using statistical methods such as the IQR (Interquartile Range) method.. Removed outliers that fall outside the +/- 5% boundaries to maintain data integrity.
	- **Feature Engineering:** Created new features from existing data to enhance the predictive power of the RFM model, such as calculating the days since the last purchase for the recency score.
	
	More details can be found in the [Jupyter Notebook](https://github.com/AspiringDSer/Olist-RFM-Analysis-Power-BI/blob/master/Olist%20-%20RFM%20Analysis.ipynb). 
	
- **Calculation of RFM Scores for Each Customer**

![[RFM Scores.png]]

- **Visualization of Segments and Insights**

![[Olist - Customer Segmentation.png]]

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

