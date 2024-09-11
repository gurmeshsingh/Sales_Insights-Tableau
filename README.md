# Sales_Insights-Tableau
# Here's a link to access Sales Insights Tableau Dashboard 
https://prod-apnortheast-a.online.tableau.com/#/site/gurmeshsingh120-38da3b6757/workbooks/2253714?:origin=card_share_link

Used MySQL and Tableau to conduct conduct data analysis of sales (revenue) and represent the findings via interactive dashboards 

## Resources: 
1.  MySQL 
2.  Tableau 
3.  Data ( provided in repo )

## Steps : 
1.  Preliminary Data Exploration using SQL 
2.  Data Cleaning & ETL through Tableau 
3.  Data Analysis of revenue using Tableau
4.  Creating interactive dashboard using Tableau


## Revenue Analysis Dashboard
![]( RevenueDashboard.png )


### Preliminary Data Exploration using SQL (Queries)
1. Show all customer records <br />
 `SELECT * FROM customers;`

2. Show total number of customers
SELECT count(*) FROM customers;

3. Show transactions for Chennai market (market code for chennai is Mark001) <br />
`SELECT * FROM transactions where market_code='Mark001'; `

4. Show distrinct product codes that were sold in chennai <br />
`SELECT distinct product_code FROM transactions where market_code='Mark001';`

5. Show transactions where currency is US dollars <br />
 `SELECT * from transactions where currency="USD"`

6. Show transactions in 2020 join by date table <br />
`SELECT transactions.*, date.* FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020;`

7. Show total revenue in year 2020, <br />
`SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and    transactions.currency="INR\r" or transactions.currency="USD\r";`

8. Show total revenue in year 2020, January <br />
`SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and and date.month_name="January" and (transactions.currency="INR\r" or transactions.currency="USD\r");`

9. Show total revenue in year 2020 in Chennai <br />
`SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.market_code="Mark001";`
