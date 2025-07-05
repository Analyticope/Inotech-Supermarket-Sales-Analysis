# Inotech-Supermarket-Sales-Analysis

## Table of Contents

 - [Project Overview](#project-overview)
 - [Data Sources](#data-sources)
 - [Recommendation](recommendations)
 - [SQL Query Used](sql-query-used)
   
   
## Inotech Sales capacity Analytics Dashboard

### Project Overview
---

This project presents a comprehensive Power BI dashboard analyzing sales data for INOTECH Supermarket. It provides key insights into total revenue, product performance, customer behavior, and payment method preferences. The goal is to assist business stakeholders in making data-driven decisions to boost sales and optimize operations.

![SCREENSHOT1](https://github.com/Analyticope/Inotech-Supermarket-Sales-Analysis/blob/main/Sales_data%2011.jpg)

![Screenshot 2](https://github.com/Analyticope/Inotech-Supermarket-Sales-Analysis/blob/main/Sales_data.jpg)

### 📄 SQL query used 
 ```sql
 List all customers from Lagos Who made a purchase above #15000
SELECT
       name,
       customer_id ,
       city,
       SUM(price) AS Total_Price
FROM Sales_data
WHERE city = 'Lagos'
GROUP BY
       name, customer_id , city
HAVING
     SUM(price) > 15000;
 ```

 ```sql
--- Show customers who have use more than one payment mode
SELECT 
    TOP 20 customer_id,
    name,
    payment_mode
FROM Sales_data
WHERE  
   customer_id IN(
   SELECT 
   customer_id 
FROM Sales_data
GROUP BY
   customer_id
HAVING COUNT
   (DISTINCT payment_mode) > 3
);
 ```

 ```sql
--- Find the Top 5 customer who have spent the most overall at Innotech Supermarket
SELECT TOP 7
     customer_id, 
     name, 
SUM(total) AS Total_spent
FROM Sales_data
GROUP BY
   customer_id, name
ORDER BY
    customer_id, name DESC;
```

 ```sql
--- Payment Meyhod Analysis
SELECT
    payment_mode,
    SUM(total) As Total_spent
FROM Sales_data
GROUP BY
payment_mode
ORDER BY
    Total_spent DESC;
```

```sql
---Sales Trend Overtime
SELECT 
    YEAR(sale_date) AS year,
    MONTH(sale_date) AS month,
   SUM(total) As Monthly_spent
FROM Sales_data
   GROUP BY YEAR(sale_date), MONTH(sale_date)
   ORDER BY  year, month DESC;
```

```sql
--- Customer by Revenue
SELECT TOP 20
    Customer_id,
    name,
  SUM(total) AS Total_spent
FROM Sales_data
GROUP BY
   Customer_id,name
ORDER BY
   Total_spent DESC;
```

### Data Sources

Sourced from well-structured CSV files, The dataset is a synthetic supermarket sales record from INOTECH Supermarket, created for analysis and portfolio purposes. It includes fields like date, city, customer, product, payment method, price, and total sales.

### Tools

- Excel
  - [Download here](https://drive.google.com/file/d/107xdkqutjEqUOOmVQMfIfoMZyp41yNVu/view?usp=drivesdk)
- Power Query - data cleaning, automate repetitive task(like fiitering, merging, and formatting).
- Building custom columns to perform specific calculations
- Power BI - Developing insightful analytics reports


  ### Data Cleaning/Preparation

  In the initial stage of this project, I performed key data structuring to ensure the dataset was clean, consistent, and analysis-ready. This phase included:
  
  1.Loading and inspecting raw data to understand its structure and quality
  
  2.Handling missing values to maintain data integrity
  
  3.Removing blank rows and irrelevant columns to streamline the dataset
  
  4.Cleaning and formatting data for consistency across all fields

### Exploratory Data Analysis

Eda Involved Exploring HR data to answer key question, such as :

8 Key Questions This Power BI Sales Analysis Project Answers:
1. What is the total sales Revenue
2.  Quantity Sold?
3.  What is the Average price?
4.  Customer Count?
5.  Sales Trend Overtime?
6.  What are the Product by Revenue?
7.  Payment Method Analysis?
8.  Customer by Revenue?
    
### Data Analysis

Tools & Features Used:

- DAX functions for custom measures and KPIs.

- Power Query for data cleaning and transformation.

- Calculated columns and measures.

- Aggregation functions (SUM, AVERAGE, COUNT etc).

- Interactive slicers and clear filter button for better UX.

### Results/Findings
1 . Sales Performance Over Time
   
• Sales revenue peaked around August and gradually declined through February, dropping from over 10 million to under 8.5 million monthly.
• Despite the monthly decline, overall year-over-year revenue increased by nearly 77%.
• However, key metrics like quantity sold, average selling price, and customer count all declined sharply.

**Finding**: The business generated more revenue from fewer sales and fewer customers,indicating either a change in sales strategy (e.g., bulk or high-value purchases) or potential data gaps.

2 . Top-Performing Products
   
• Products such as Always Pads (₦3.6M), Chi Exotic (₦3.4M), and Bobo Juice (₦2.8M) were the highest revenue generators.
• Most top products are fast-moving consumer goods, especially beverages and household items.

**Finding**: These products are key revenue drivers and likely have strong, consistent demand. They should be prioritized in stock planning and promotions.

3 . City-wise Revenue Distribution
   
• The highest revenue came from Lagos and Benin City (₦8M each), followed by Uyo, Calabar, Enugu, and Ilorin, all generating over ₦7M.

**Finding**: Sales are fairly balanced across multiple cities, indicating good regional reach and performance.

4 . Customer Revenue Contribution
   
• A small group of customers, like Alison Ryan (₦114K) and Alicia Neal (₦106K), contributed significantly to total sales.

**Finding**: The business heavily depends on a few high-value customers, which presents both opportunity and risk. Retaining these customers is critical.

  ### Recommendation
1 . Address the Sales Decline Over Time
    Look into why sales have been dropping month by month,it could be due to seasonality, stock issues, or lack of promotions. Try running targeted marketing campaigns 
    during slower months to boost sales.

2 . Keep Best-Selling Products in Focus
   Always Pads, Chi Exotic, and Bobo Juice are strong performers. Make sure these are always in stock and consider bundling them with other products to drive more sales.
   
3 .Learn From Top-Performing Cities
   Lagos and Benin City are leading in revenue. Study what’s working in those cities and try to apply the same strategies (ads, pricing, promotions) in lower-performing 
   areas.
   
4 .Prioritize High-Value Customers
  A few customers are spending a lot — they’re clearly valuable. Show appreciation with loyalty rewards, personalized offers, or exclusive discounts to keep them coming 
  back.
  
5 .Support All Payment Methods
   Customers are using a variety of payment options almost equally. Keep offering this flexibility, but you might consider encouraging digital payments with small 
   incentives like cashback or discounts.
   
6 .Investigate Drops in Quantity, Price, and Customer Count
  Even though revenue is up, fewer people are buying, and fewer items are being sold. Check if this is due to a reporting issue or if the business is shifting to fewer, 
   larger sales — and adjust your strategy accordingly.

    
### Conclusion
This analysis shows that INOTECH Supermarket is doing well overall,revenue has grown significantly year-over-year, which is a great sign. But beneath that surface, there are a few things that need attention.

The good news? There are clear strengths to build on:
• Some products consistently drive revenue.
 
• Certain cities are performing exceptionally well.
 
• Top customers are loyal and valuable.
 
• Payment systems are flexible and working smoothly.

With a few smart moves — like focusing on customer engagement, promoting best-selling products, and improving performance in slower months,INOTECH can turn these insights into action and keep growing in the right direction.






