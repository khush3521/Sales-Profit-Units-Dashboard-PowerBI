# Sales-Profit-Units-Dashboard-PowerBI
Power BI report analysing sales, profit and units sold using global financial dataset.


## Objective
- Analyse sales, profit and units sold across segment, product and country to identify
- high-performing areas and loss-making combinations.

## Dataset
- Columns: Segment, Country, Product, Units Sold, Sale Price, Gross Sales,
  Discounts, Sales, Cost of Goods Sold, Profit, Date, Year, Month, Status (profit/break-even/loss).

## Tools
- Power BI Desktop
- Power Query (data cleaning)
- DAX (measures for Sales, Profit, Units, Profit Margin)

## Report Pages
1. **Sales Overview** – KPIs, sales trend, sales by segment/country, top products.
2. **Profit Analysis** – profit trend, profit margin, profit by product/segment,
   loss vs profit using status.
3. **Units Sold Analysis** – volume trend, units by segment/country/product.

## Key Insights (example)
- Government & Channel Partners segments generate highest sales.
- Certain products have high sales but low profit margin due to discounts.
- Loss transactions are concentrated in Enterprise segment for some products.

## Screenshots
- sales :-  https://github.com/khush3521/Sales-Profit-Units-Dashboard-PowerBI/blob/main/Screenshot%202025-11-27%20222756.png
-   profit :- https://github.com/khush3521/Sales-Profit-Units-Dashboard-PowerBI/blob/main/Screenshot%202025-11-27%20222812.png
  -   unit :- https://github.com/khush3521/Sales-Profit-Units-Dashboard-PowerBI/blob/main/Screenshot%202025-11-27%20222823.png

## Report for 3 Dashboard
# sales
1. What is the total sales revenue for the selected period?
- The total sales generated is 118.73M.

2. How much Gross Sales and Discount were offered overall?
- Total Gross Sales: 127.93M
- Total Discount Given: 9.21M
  
3. Which month recorded the highest sales?
- October recorded the highest sales with around 21.7M, followed by December (~17.4M).

4. Which month had the lowest sales?
- June had the lowest sales (~5.6M).

5. Which customer segment contributes the most to total sales?
- The Government segment has the highest sales at 53M, followed by Small Business (42M).

6. Which product generates the highest sales?
- Paseo is the top-selling product with 33M in total sales.

7. Which countries contribute the most to sales?
- Sales are strongest in North America (USA & Canada) followed by Germany and France.

# Profit

1. What is the total profit and profit margin?
- Total Profit: 16.89M
- Profit Margin: 14% (0.14)

2. Which segment is the most profitable?
- The Government segment is the most profitable with 11.4M profit.

3. Which segment is making losses?
- The Enterprise segment shows a loss of -0.6M.

4. Which product generates the highest profit?
- Paseo again leads with 4.8M profit.

5. How does profit trend month-by-month?
- Profit peaks in October (3.4M) and dips in March–April, staying below 1M.

6. Which countries show highest profitability?
- Across segments, the highest profitability is seen in:
 -- Canada
-- France
-- USA
- The matrix shows Government and Channel Partners contribute most to profits.

7. What does the profit status (Increase / Decrease / Total) indicate?
- The waterfall chart shows:
- Profit increases mainly from Government & Small Business
- Profit decreases from Enterprise & Midmarket
- Loss status also impacts overall margin
