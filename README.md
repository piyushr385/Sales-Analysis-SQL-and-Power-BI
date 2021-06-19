# Sales-Analysis-SQL-and-Power-BI

## Problem Statement: 
`Our case study is based on a computer hardware business which is facing challenges in dynamically changing market. 
Sales director decides to invest in data analysis project he would like to build power BI dashboard that can give him real time sales insights.`

## Objective:
`To unlock sales insights that are not visible before the sales team for decision and support automate them to reduced manual time spent in data gathering and 
develop a power bi dashboard for the sales manager for real time sales insight so he can observe the sales of 
different regions daily and keep a track to take actions where sales are not increasing.`

## Dashboard:
1. **Key Insights**

<img src='Report/Key insights.jpg' width="700">

2. **Profit Analysis**

<img src='Report/Profit analysis.jpg' width="700">


## Database and Technologies Used:
* MYSQL-Database 
* SQL
* Power BI

## Steps:
* Load the database file in MYSQL workbench.
* Perform Data-Analysis using SQL Queries.
* Load the Data in Power BI.
* Transform the data.
* Create some new Measures in Power BI.
* Create visuals and Dashboards.

## SQL queries for Data-Analysis:

1. Show all customer records

    `SELECT * FROM customers;`
    

2. Show total number of customers

    `SELECT count(*) FROM customers;`


3. Show transactions for Chennai market (market code for chennai is Mark001

    `SELECT * FROM transactions where market_code='Mark001';`



4. Show distrinct product codes that were sold in chennai

    `SELECT distinct product_code FROM transactions where market_code='Mark001';`



5. Show transactions where currency is US dollars

    `SELECT * from transactions where currency="USD"`


6. Show transactions in 2020 join by date table

    `SELECT transactions.*, date.* FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020;`
 
 
 7. Show total revenue in year 2020,

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date 
     where date.year=2020 and transactions.currency="INR" or transactions.currency="USD";`


8. Show total revenue in year 2020, January Month,

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and 
     date.month_name="January" and (transactions.currency="INR\r" or transactions.currency="USD\r");`



9.Show total revenue in year 2020 in Chennai

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020
     and transactions.market_code="Mark001";`


## Data Analysis Using Power BI:

* Different Formulas used for creating measures:

1. `Revenue = SUM('sales transactions'[norm_amount])`

2. `Sales Qty = SUM('sales transactions'[sales_qty])`

3. `Total profit margin = SUM('sales transactions'[profit_margin])`

4. `Profit margin % = DIVIDE([Total profit margin], [Revenue], 0)`

5. `profit margin contribution % = DIVIDE([Total profit margin],CALCULATE([Total profit margin],ALL('sales products'),ALL('sales customers'),ALL('sales markets')))`

6. `Revenue contribution % = DIVIDE([Revenue],CALCULATE([Revenue],ALL('sales products'),ALL('sales customers'),ALL('sales markets')))`


## End Result:
* An automated dashboard providing quick and latest sales insights in order to support data driven decision making.

## Success Criteria:
*	Dashboard uncovering sales order insights wih the latest data available.
*	Sales team able to take better decision and prove 10% cost savings of total spend.
*	Sales analyst stop gathering data manually in order to save 20% of their business time and reinvest in value added activity.

## Future Work:
* Update the Dashboard according to the Feedback of the Stakeholders and Sales Managers.

