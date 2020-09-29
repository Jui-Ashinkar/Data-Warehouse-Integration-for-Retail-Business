# Data-Warehouse-Integration-for-Retail-Business

**Objective**


• Developed Multi-Dimensional data model (STAR Schema) and enhanced it to meet growing requirements

• Created a centralized data warehouse, pipelining retail data from diverse data sources using Talend Implemented Slowly Changing Dimensions, Rejection codes, and performance tuning on a dataset with 48 million rows

• Built interactive dashboards to convey stories of retail sales and customer segmentation using Tableau and PowerBI


**Overview**


• This project involves a retail company that sells a variety of products to people and to businesses across a variety of sales channels


• The Retail Company would like to: Create a data warehouse (DW) from its various systems of record (SORs) Create BI applications that enable analysis of business performance

• The DW will store (facts) in the following subject areas: Sales Inventory Sales Quotas Strategy Plans



**Retail**

The categories of products sold: Audio TV and Video Computers Cameras and camcorders Cell phones Music, Movies and Audio Books Games and Toys Home Appliances The Retail Company would like to: Create a data warehouse (DW) from its various systems of record (SORs) Create BI applications that enable analysis of business performance

**Observations in SOR**

• Different unique key for product’s table across all SORs e.g. ProductID, BrandID, ProductLabel

• Length of the values were different across SORs

• Data type for dates in the CSV and TXT files are not constant



**Data Profiling**

• Changed the SOR Load and Update dates from TIMESTAMP to DATE for Oracle and PostgreSQL to load SOR_LOADDATE

• Converted data type values for DATES to DATE data type across all the CSVs and Text input files

• For SCDs DimProductPrice and DimProductCost we had to use SOR dimproduct (MySQL) as a bridge between input file price_cny_step_1_of_4 and DIMPRODUCT

• Converted all the possible columns in the target metadata from Big Decimal to INT

• Data Type csv contains all the column’s data type which we kept constant across all the SORs and Target table depending upon the size of data

• Had to append zeros and trimmed values in the for joining product tables


**Reject Codes and Error Handling**

• Reject Codes are used to catch bad data,missing values or invalid data present in the facts rejects

• Reject Reasons help you understand the bad data in detail

• Handled null values using Relation.ISNULL function and applied code 99 if nulls are found

**Master Job**
![MasterJob](https://user-images.githubusercontent.com/56845665/94502879-20813d00-01d3-11eb-9668-d930906cd9be.PNG)

**PowerBI Visualizations**

<img width="468" alt="1" src="https://user-images.githubusercontent.com/56845665/94502951-4eff1800-01d3-11eb-8998-367ecd9d1417.png">
<img width="468" alt="2" src="https://user-images.githubusercontent.com/56845665/94502952-50304500-01d3-11eb-9da8-aa5ed8688cf5.png">
<img width="468" alt="3" src="https://user-images.githubusercontent.com/56845665/94502957-51fa0880-01d3-11eb-995a-173e69dcfd27.png">
<img width="468" alt="4" src="https://user-images.githubusercontent.com/56845665/94502966-558d8f80-01d3-11eb-95a8-abe60fcd5a4e.png">


**Tableau Visualizations**
<img width="468" alt="5" src="https://user-images.githubusercontent.com/56845665/94503018-79e96c00-01d3-11eb-9f10-300c0a03b2d7.png">
<img width="468" alt="6" src="https://user-images.githubusercontent.com/56845665/94503020-7a820280-01d3-11eb-9ee0-365eb562aaeb.png">
<img width="468" alt="7" src="https://user-images.githubusercontent.com/56845665/94503022-7bb32f80-01d3-11eb-9981-32b5c2726475.png">
<img width="468" alt="8" src="https://user-images.githubusercontent.com/56845665/94503025-7ce45c80-01d3-11eb-987d-0c8019e52c04.png">
<img width="468" alt="9" src="https://user-images.githubusercontent.com/56845665/94503028-7eae2000-01d3-11eb-94ef-6340bdc42adc.png">
<img width="468" alt="10" src="https://user-images.githubusercontent.com/56845665/94503032-81107a00-01d3-11eb-89a0-c3889dc879ef.png">
<img width="468" alt="11" src="https://user-images.githubusercontent.com/56845665/94503038-82da3d80-01d3-11eb-94f7-6e37fa247ecc.png">
