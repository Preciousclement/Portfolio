# Superstore Sales Analysis
This project involves analyzing sales data from a fictional superstore to uncover key business insights. 

## Table of Content
- [Project Overview](#project-overview)
- [Data Source](#data-source)
- [Tools Used](#tools-used)
- [Objectives](#objectives)
- [Steps Taken](#steps-taken)
- [Key Insight for 2023](#key-insight-for-2023)
- [Conclusion](#conclusion)

  
### Project Overview
The analysis of this project includes exploring sales patterns, previous year perfomance from current year, product performance, profits and regional trends . 
Using Excel and Tableau, the project aims to provide actionable recommendations for optimizing inventory, improving sales strategies, and enhancing customer satisfaction.

### Data Source 
The primary data set used for this analysis is from kaggle.com
The dataset consists of 9,995 rows with the folllowing attributes; Row ID, Order ID,	Order Date,	Ship Date,	Ship Mode,	Customer ID,	Customer Name,	Segment,	Country,	City,	State,	Postal Code,	Region,	Product ID,	Category,	Sub-Category,	Product Name,	Sales	Quantity,	Discount and	Profit	 	 

### Tools Used
- Excel
- Tableau 

### Objectives
1. Data Cleaning: Ensure data integrity by addressing inconsistencies, such as date formatting issues and missing values.
2. Exploratory Data Analysis (EDA): Identify trends and patterns within the data.
3. Visualization: Create visual representations of the insights to facilitate understanding and decision-making.

### Steps Taken
#### 1. Analyzed Requirements
- Understood the data
- The right requirements we collected, the right charts were choosen, as well as the colors
- Drew a mockup for guidance

#### 2. Building Data Source & Charts
- Data was cleaned with Excel
- Data was connected to Tableau and data model created
- Renamed fields and tables
- Crosschecked data types

#### 3.  Created Calculated Fields:
- Current Year, Previous Year
- CY of Profit, Sales, Quantity, Orders and Customers
- PY of Profit, Sales, Quantity, Orders and Customers
- Min/Max of Profit, Sales, Quantity, orders and Customers
- % Difference of Profit, Sales, Quantity, orders and Customers
  
- Inputed a "select year" parameter
- Build charts accordingly
- Formatted the charts by cleaning up axis & headers. coloring and tooltip

**CALCULATED FIELDS CREATED**
1. **Formular was also used for CY profit, quantity and orders**
-- CY of Sales --
IF YEAR([Order Date]) = [Select Year] THEN [Sales]
END

-- CY Customer --
IF YEAR([Order Date]) = [Select Year] THEN [Customer ID] 
END


2. **Formular was also used for PY profit, quantity and orders**
-- PY of Sales --
IF YEAR([Order Date]) = [Select Year] - 1 THEN [Sales]
END

-- PY Customers --
IF YEAR([Order Date]) = [Select Year] - 1 THEN [Customer ID] 
END

3. **Formular was also used for % Diff of profit, quantity and orders**
-- % Difference of Sales between years --
(SUM([CY Sales]) - SUM([PY Sales])) / SUM([PY Sales])

-- % Difference of Customers between years --
(COUNTD([CY Customers]) - COUNTD([PY Customers])) / COUNTD([PY Customers])


4. **Formular was also used for Min/Max of profit, quantity and orders**
-- Min/Max of Sales --
IF SUM([CY Sales])= WINDOW_MAX(SUM([CY Sales]))
THEN SUM([CY Sales])
ELSEIF SUM([CY Sales])= WINDOW_MIN(SUM([CY Sales]))
THEN SUM([CY Sales])
END

-- Min/Mx of Customers --
IF COUNTD([CY Customers]) = WINDOW_MAX(COUNTD([CY Customers]))
THEN COUNTD([CY Customers])
ELSEIF COUNTD([CY Customers]) = WINDOW_MIN(COUNTD([CY Customers]))
THEN COUNTD([CY Customers])
END


```
#### 3. Dashboard Setup
- Drew Mockups for containers
- Built the container stgructures
- Pull all the charts together
- Formatted the charts by distributing evenly, including legends and adding inner & outer paddings
- Included Icons, Filter and Dynamics
  
**Dashbord**

Published on Tableau Public(Dynamic): [View Tableau Visualization]([https://link-to-your-tableau-visualization](https://public.tableau.com/views/SuperstoreSales2_17260991531630/CustomersDashboard?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)




<img width="652" alt="Screenshot 2024-09-12 014454" src="https://github.com/user-attachments/assets/51c43ccb-4368-4d0e-a0ab-81dd46b0b999">

<img width="651" alt="Screenshot 2024-09-12 014511" src="https://github.com/user-attachments/assets/59ebaa28-35ea-4edb-bd7e-717a6b3c6236">



### Key Insight for 2023

1. **Overall Sales Performance:**
   - **Total Sales:** The total sales for 2023 reached **$733k**, which is a **20.4% increase** compared to the previous year, showcasing a positive growth trend.
   - **Total Profit:** Profits for the year totaled **$93k**, reflecting a **14.2% increase** year-over-year.
   - **Total Quantity Sold:** A total of **12k units** were sold in 2023.

2. **Sales & Profit Trend:**
   - The **average sales per month** for 2023 were **$14k**, while the **average profit per month** was **$2k**. This steady trend reflects consistent performance throughout the year.

3. **Customer Growth & Sales per Customer:**
   - In 2023, we saw a total of **693 customers**, which is an **8.6% increase** compared to the previous year.
   - The **average sales per customer** was **$1,058**, representing a **20.4% increase** year-over-year, indicating stronger spending or larger orders from the customer base.

4. **Total Orders:**
   - The total number of orders for 2023 was **1,687**, with a **28.3% increase** compared to 2022, highlighting strong purchasing behavior.

5. **Regional Sales Distribution:**
   - The **West region** led in total sales, followed by the **East**, then **Central**, and lastly, the **South**. This breakdown points to stronger market penetration in the Western and Eastern regions.

6. **Top 10 Customers by Profit:**
   - The top 10 customers in 2023 contributed significantly to profits, with the highest-earning customer generating **$6,781** in profit and **$14,023** in sales. This emphasizes the importance of high-value customers to the overall profit margins.

### Conclusion

2023 marked strong growth with a **20.4% sales increase** and **14.2% profit rise**. Higher order volumes and customer engagement, especially from top clients, drove success. The **West region** led in sales, while other regions also showed growth potential. Moving forward, the focus should be on optimizing customer relationships and expanding regional efforts to sustain momentum.


[Back to Portfolio](./index.md)
