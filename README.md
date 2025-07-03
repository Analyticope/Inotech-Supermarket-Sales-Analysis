# Inotech-Supermarket-Sales-Analysis

## Table of Contents

 - [Project Overview](#project-overview)
 - [Data Sources](#data-sources)
 - [Recommendation](recommendations)
   
## HR Workforce capacity Analytics Dashboard

### Project Overview
---

In this HR analytics project, I developed a in-depth Power BI dashboard by integrating insights from three separate text files: Employee Data, Training & Development, and Recruitment.After performing thorough data cleaning and transformation, I utilized DAX to build custom measures and KPIs, enabling dynamic analysis of key HR metrics.

![SCREENSHOT1](https://github.com/Analyticope/Inotech-Supermarket-Sales-Analysis/blob/main/Sales_data%2011.jpg)


![Screenshot 2](https://github.com/user-attachments/assets/bd66b9a8-e43b-4bc9-9ce3-0d5ce214afdd)

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

### Data Sources

Sourced from well-structured CSV files, the data offers a well-rounded insight of the employee journey—from recruitment and onboarding to training and professional development.

### Tools

- Excel
  - [Download here](https://microsoft.com)
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

10 Key Questions This Power BI HR Project Answers:

1. What is the average salary across departments?

2. How many employees are currently active?

3. What is the gender breakdown of the workforce?

4. What is the total cost spent on training?

5. How many offer and rejection letters were issued?

6. What is the race and ethnicity distribution?

7. How does racial diversity vary across the company?

8. How do employee ratings differ by department?

9. What is the employee count by state?

10. How are applications distributed by recruitment status?
    
### Data Analysis

Tools & Features Used:

- DAX functions for custom measures and KPIs.

- Power Query for data cleaning and transformation.

- Calculated columns and measures.

- Custom columns and “Column by Example”.

- Aggregation functions (SUM, AVERAGE, COUNT etc).

- Interactive slicers and clear filter button for better UX.

### Results/Findings

This HR Analytics Dashboard delivers actionable insights into the organization’s workforce. Key findings include:

- Average Salary: $65K across 991 active employees, with an average age of 42.

- Gender Distribution: 668 males (56%) and 865 females (44%), totaling 1,533 employees.

- Training Investment: $2M total training cost, with $1.67M attributed to training outcomes.

- Applications Overview: 1,997 applications processed.

- Additional Insights:

    - Exit trends by department

    - Average employee contract types

   - Application status distribution

   - Workforce spread across states and departments

  ### Recommendation

     Based on the HR analysis, we recommend investigating gender disparities within the recruitment pipeline to ensure equal opportunity hiring. Special attention 
     should be given to employees exiting under the “Needs Improvement” category, as this may indicate deeper issues with performance management or onboarding. 
     Additionally, evaluating the cost-effectiveness of training programs can help optimize learning investments and improve outcomes. Finally, a closer look at employee 
     distribution across departments can support more strategic workforce planning and better resource allocation.

### Limitations

During the development of the HR dashboard, I encountered limitations related to inconsistent and unnecessary data, particularly with date fields and blank rows. These issues affected the accuracy of filtering and overall dashboard performance. To resolve this, I cleaned and transformed the data using tools in the Power Query ribbon removing redundant entries and handling null values to ensure smooth functionality and prevent potential breakdowns in the analysis.


💻



