# Sales-Insights-AtliQ-Hardware

## PROBLEM STATEMENT :

AtliQ Hardware is a company which supplies computer hardware and peripherals to many of clients such as Surge Stores, Nomad stores, Excel Stores, Electricalsara Stores etc. across India. The head office of AtliQ Hardware  is based out of  Delhi, India and they have many regional office throughout the India.

The Sales Director of this company is facing a lot of challenges. The market is growing dynamically and he is facing issues in terms of tracking the sales in this dynamically growing market and the insights of the business, as overall sales was declining. He has regional manager for North India, South and Central India. Whenever he wants to get some insights of these region he would call the managers from the respective regions and the regional managers would give him the required insights like what was the sales last quarter and how they are going to grow by this much in the next quarter.

Now the problem was, these regional managers were not giving any proofs with facts. Even though he could he the overall sales declining, he was not getting any clear picture as to why this was happening. AtliQ Hardware being a big business, it was very important to see the insights clearly to take any kind of data driven decisions, which could help with the increase in sales of his company. 
So he wants a simple data visualization tool which he can access on daily basis. By using such tools and technology he can make data driven decisions which in turn helps to increase the sales of the company. So, In this projects we will help AtliQ Hardware to make its own sales related dashboard using power BI.


## DATA DISCOVERY :

AIMS Grid - It is a project management tool which consists of four components-
	○ Purpose - (What to do exactly)
	○ Stakeholder - (Who will be involved)
	○ End result - (What do you want to achieve)
  ○ Success Criteria - (Cost optimization and time save)


AIMS Grid for Sales Analysis of AtliQ Hardware:

1. Purpose :- To unlock sales insights that are not visible before for the sales them for decision support and automate them to reduced manual time spent in data gathering.

2. Stakeholders :-
	○ Sales Director
	○ Marketing Team
	○ Customer Service Team
	○ Data and Analytics Team
	○ IT

3. End result :- An automated dashboard providing quick and latest sights in order to support Data driven decision making.

4. Success Criteria :-
	○ Dashboard uncovering sales order insights with latest data available.
	○ Sales team able to take better decisions and prove 10% cost saving of total spend.
	○ Sales analysis stop data gathering manually in order to save 20% business time and invest in value added activity.


## BASIC ANALYSIS OF THE SALES DATABASE :

1.To find of all customers records

```sql
SELECT * FROM sales.customers;
```

2.To find total number of customers
```sql
SELECT count(*) From sales.customers;
```

3.To find transactions for Chennai market (market code for chennai is Mark001)
```sql
SELECT * FROM sales.transactions where market_code='Mark001';
```

4.To find distrinct product codes that were sold in chennai
```sql
SELECT distinct product_code FROM sales.transactions where market_code='Mark001';
```

5.To find transactions for Mumbai market (market code for chennai is Mark002)
```sql
SELECT * FROM sales.transactions where market_code='Mark002';
```

6.To find distrinct product codes that were sold in Mumbai
```sql
SELECT distinct product_code FROM sales.transactions where market_code='Mark002';
```

7.To find transactions where currency is US dollars
```sql
SELECT * from sales.transactions where currency="USD";
```

8.To find transactions in 2020 
```sql
SELECT sales.transactions.*, sales.date.*
FROM sales.transactions
INNER JOIN sales.date
ON sales.transactions.order_date=sales.date.date
where sales.date.year=2020;
```

8.To find transactions in 2019 
```sql
SELECT sales.transactions.*, sales.date.*
FROM sales.transactions
INNER JOIN sales.date
ON sales.transactions.order_date=sales.date.date
where sales.date.year=2019;
```

9.To find total revenue in year 2020
```sql
SELECT SUM(sales.transactions.sales_amount) as Total Revenue
FROM sales.transactions
INNER JOIN sales.date
ON sales.transactions.order_date=sales.date.date
where sales.date.year=2020 and sales.transactions.currency="INR\r" or sales.transactions.currency="USD\r";
```

10.To find total revenue in year 2019
```sql
SELECT SUM(sales.transactions.sales_amount) Total Revenue
FROM sales.transactions
INNER JOIN sales.date
ON sales.transactions.order_date=sales.date.date
where sales.date.year=2019 and sales.transactions.currency="INR\r" or sales.transactions.currency="USD\r";
```

11.To find total revenue in January, 2020
```sql
SELECT SUM(sales.transactions.sales_amount) Total Revenue
FROM sales.transactions
INNER JOIN sales.date
ON sales.transactions.order_date=sales.date.date
where sales.date.year=2020
and sales.date.month_name="January"
and (sales.transactions.currency="INR\r" or sales.transactions.currency="USD\r");
```

12.To find total revenue in February, 2020
```sql
SELECT SUM(sales.transactions.sales_amount) Total Revenue
FROM sales.transactions
INNER JOIN sales.date ON sales.transactions.order_date=sales.date.date
where sales.date.year=2020
and sales.date.month_name="February"
and (sales.transactions.currency="INR\r" or sales.transactions.currency="USD\r");
```

13.To find total revenue in January, 2019
```sql
SELECT SUM(sales.transactions.sales_amount) Total Revenue
FROM sales.transactions
INNER JOIN sales.date
ON sales.transactions.order_date=sales.date.date
where sales.date.year=2020
and sales.date.month_name="January"
and (sales.transactions.currency="INR\r" or sales.transactions.currency="USD\r");
```

14.To find total revenue in February, 2019
```sql
SELECT SUM(sales.transactions.sales_amount) Total Revenue
FROM sales.transactions
INNER JOIN sales.date ON sales.transactions.order_date=sales.date.date
where sales.date.year=2020
and sales.date.month_name="February"
and (sales.transactions.currency="INR\r" or sales.transactions.currency="USD\r");
```

15.To find total revenue in year 2020 in Chennai
```sql
SELECT SUM(sales.transactions.sales_amount) Total Revenue
FROM sales.transactions
INNER JOIN sales.date ON sales.transactions.order_date=sales.date.date
where sales.date.year=2020 and sales.transactions.market_code="Mark001";
```

16.To find total revenue in year 2020 in Mumbai
```sql
SELECT SUM(sales.transactions.sales_amount) Total Revenue
FROM sales.transactions
INNER JOIN sales.date
ON sales.transactions.order_date=sales.date.date
where sales.date.year=2020 and sales.transactions.market_code="Mark002";
```



## Data Cleaning and ETL (Extract, Transform, Load):

After the basic analysis, we will work on data cleaning and ETL.

Step 1: Connect the MySQL database with the PowerBI desktop.
Step 2: Loading data into the Power BI deskstop and pull data from SQL.









