# Sales Analysis for Electronic Retail Store 
[Inspired by Keith Galli's video: Solving real world data science tasks with Python Pandas!](https://www.youtube.com/watch?v=eMOA1pPVUc4&list=PLD27DiVmJtrTPYCW_VIn8k9EvrzvJPV0k&index=17)

#### NOTE: I have used SQL and Power BI DAX for my data analysis and visualization. 

# Resources Used for this Project: #
- Stack Overflow and other online forums to research DAX and SQL queries.
- Cole Nussbaumer Knaflic's book, *Storytelling with Data*, to reference best practices for data visualization. 

# Summary: #
The objective of this project is to analyze sales data for an electronic retail store operating in the United States. By identifying patterns and insights, I aim to answer important business questions related to performance, customer behavior, and market trends. The findings will inform decisions regarding product offerings, pricing, promotions, and marketing strategies to drive growth and success for the business.

# Business Questions: #
- Q1. What was the best month for sales? How much was earned that month?
- Q2. What city had the highest number of sales?
- Q3. What time should we display advertisements to maximize likelihood of customer's buying product?
- Q4. What products are often sold together? 
- Q5. What product so the most? Why do you think it sold the most?  

# Discovery: #
- The project involves working with 12 CSV files, each representing a month of the year.
- All 12 files share a common structure, consisting of six columns capturing Order ID, Product, Quantity, Price Each, Order Date, and Purchase Address.
- Each file contains over 9000 rows of data, providing comprehensive transactional details.
- While some missing values exist, the dataset's overall shape is consistent, providing adequate data for analysis.
- To proceed with further structuring, the next step is to import the data into Microsoft SQL Server Management Studio. 

# Joining: #
- The dataset was loaded using the import wizard from SSMS.
- A SQL query was used to combine the 12 months of sales data into one source table.
- A backup of the merged dataset was created to ensure data safety during further transformations.

# Cleaning, Structuring, and Validating: #
- Rows with missing values in the [Order ID] column were removed since they were deemed unnecessary for analysis.
- A calculated column named [Sales Price] was created by multiplying the [Price Each] and [Quantity Ordered] columns to represent the sales prices.
- The [Order Date] datetime column was split into multiple columns, including date, year, month, day, time, hour, and minutes, to provide more granular data for deeper analysis.
- The [Purchase Address] column was also split into multiple columns, including street, city, state, and zipcode, to allow for more granular data analysis.
- The dataset was validated using custom queries within the RDBMS, leveraging joins, subqueries, and common table expressions (CTE) to answer business questions.
- No unusual results were discovered during the validation process, allowing me to proceed to visualize the data using Microsoft Power BI.

# Presenting: #
- To model my dataset, I utilized the Star Schema approach, creating separate Fact and Dimension tables in SQL and populating them with values from the original source table.
- The process involved creating unique keys and custom SQL VIEWS to join the dimension table to the fact table, ensuring accurate data representation.
- The Fact table comprised of two tables, Fact_orders and FACT_market_baskets, while the Dimension table was made up of DIM_products, DIM_store, and DIM_date.
- To finalize the data visualization, I created relationships between the tables in Power BI and incorporated DAX to generate calculated measures for my dashboard/report.

# Dashboard: #
![Dashboard Overview](https://user-images.githubusercontent.com/28738970/233511744-eb250534-1e67-40ca-b9cd-f37291ddea70.png)

# My Analysis: #
- Q1. What was the best month for sales? How much was earned that month?

- Answer: The highest sales of over $4.61 million were achieved in December. 

  ![image](https://user-images.githubusercontent.com/28738970/233812139-5b5f38c0-faa0-406e-8a52-d4395dbc39f9.png)

- Q2. What city had the highest number of sales?

- Answer: The city with the highest sales was San Francisco, which amounted to $8.25 million. The second highest was Los Angeles at $5.45 million, followed by New York City at $4.66 million.

  ![image](https://user-images.githubusercontent.com/28738970/233812241-dd42be7d-cc0e-4602-9e30-d6573120fb45.png)

- Q3. What time should we display advertisements to maximize likelihood of customer's buying product?

- Answer: According to the chart, the peak sales time occurred at 11:58 AM, with 281 products sold, followed by 1:25 PM with 271 products sold, 8:13 PM with 269 products sold, 11:26 AM with 268 products sold, and 6:36 PM with 262 products sold. Based on this trend, advertising between 11:00 AM to 2:00 PM midday and 6:30 PM to 9:30 PM would be most effective, as sales start to decrease steadily after this time frame.

  ![image](https://user-images.githubusercontent.com/28738970/233812431-e4c1dde6-6d37-40f4-9eda-c45547b2b96a.png)


- Q4. What products are often sold together? 

- Answer: The data shows that the USB-C Charging cable was the product that customers most frequently purchased together, with 2208 sales, followed closely by the iPhone with 2018 sales, and wired headphones with 1856 sales. The lightning charging cable, Google phone, and Apple Airpods were also popular purchases. These insights suggest that customers prefer to buy devices along with accessories and power cables. To maximize sales, it would be wise to market these items together with promotions or place them in close proximity to each other.

  ![image](https://user-images.githubusercontent.com/28738970/233812619-5a58e247-2903-46cc-9feb-07975ccb00a9.png)

- Q5. What product sold the most? Why do you think it sold the most?  

- Answer: According to the chart, the top-selling products are AAA Batteries (4-pack), AA Batteries, USB-C Charging Cable, and Lightning Charger. This trend may be attributed to the importance of power-related products for electronic devices. It is noteworthy that the top-selling products are also the cheapest per unit. However, the top-earning products are the MacBook Pro Laptop, iPhone, ThinkPad Laptop, and Google Phone, with little influence from products in the top-selling list. To maximize sales and earnings, it would be wise to balance prices and offer promotions for the top-earning products to increase the likelihood of increasing sales and maximize profits.

  ![image](https://user-images.githubusercontent.com/28738970/233812803-0a386869-ffc9-4bfd-aa2e-ce5764b689ea.png)
  ![image](https://user-images.githubusercontent.com/28738970/233812816-c2ff3051-d5d8-45b9-ba46-72409ca3225e.png)
