# 📊 Power BI Implementation Notes

This folder contains the Power BI part of my AWS E-Commerce Analytics project.

After preparing the data in Amazon Athena, I connected Power BI using the Simba Athena ODBC Driver and built an interactive dashboard to analyze sales, profit, customers, and regional performance.

---

## 🔌 Connecting Power BI to Athena

The first step was connecting Power BI to Amazon Athena using the Simba Athena ODBC Driver.

I imported the tables that I needed for the dashboard.

### Tables Used

- vw_orders_clean
- order_details
- sales_target

### What I learned

This helped me understand how Power BI can connect directly to cloud data instead of using a local database.

---

## 🔗 Data Model

After importing the tables, I created relationships between them.

I made sure the relationships were correct before building any visuals because I learned that a good data model is important for getting accurate results.

### What I learned

I understood why relationships are important and how they affect filters and calculations inside Power BI.

---

## 🧮 DAX Measures

Instead of using the columns directly, I created DAX measures for the KPIs.

### Measures Created

- Total Sales
- Total Profit
- Total Orders
- Total Customers
- Profit Margin
- Average Order Value

### What I learned

Creating DAX measures helped me understand how Power BI performs calculations based on filters and slicers.

---

## 📈 Executive Dashboard

After creating the measures, I started building the dashboard.

I wanted the dashboard to answer some basic business questions like:

- How much did the business sell?
- Which category performs the best?
- Which states have the highest sales?
- Who are the top customers?
- How are sales changing over time?

### What I learned

I learned that choosing the right visual is just as important as the data itself. A simple and clean dashboard is much easier to understand.

---

## 💡 Business Insights Page

For the second page, I focused on summarizing the important findings instead of adding more charts.

I wrote business insights and recommendations based on the dashboard so that anyone looking at the report could quickly understand the results.


### What I learned

This part of the project helped me understand that dashboards should not only show data but also explain what the data means.

---


## 💡 Key Takeaways

This project gave me practical experience with:

- Connecting Power BI to Amazon Athena
- Building a data model
- Creating DAX measures
- Designing an interactive dashboard
- Converting data into business insights

Overall, this project helped me understand the complete process of creating a business intelligence dashboard using AWS and Power BI.
