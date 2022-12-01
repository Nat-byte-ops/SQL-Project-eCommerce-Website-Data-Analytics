# SQL-eCommence-Website-Data-Analysis

## Background

This is an eCommerce Database Analytics Project for a start-up, an online retailer which has just launched their first product. We'll analyze the company's 4 years website and order data.

## Goals

Using SQL to:

- Access and explore the company's database
- Analyze and optimize the business' marketing channels, measure and test website conversion performance
- Building conversion funnels
- Use data to understand the impact of new product launches

## Main Tasks

- [ ] Analyzing Traffic Sources:

* 1. Top traffic sources
* 2. Bid Optimization & Trend Analysis

- [ ] Analyzing Website Performance:

* 1. Top website pages & entry pages
* 2. Bounce rates & Landing Page
* 3. Building conversion funnels & Testing conversion rates

- [ ] Analysis for Channel Portfolio Management:

* 1. Analyzing Channel Portfolios
* 2. Direct, Brand-Driven Traffic

- [ ] Analyzing Business Patterns and Seasonality
- [ ] Product Analysis

* 1. Product Sales & Product Launches
* 2. Product-level Website Pathing
* 3. Cross-Selling & Product Portfolio Analysis
* 4. Analyzing Product Refund Rates

- [ ] User Analysis: Repeat Visit & Purchase Behavior

## Overview of the Company Database

<img width="765" alt="Screen Shot 2022-05-08 at 11 22 37 am" src="https://user-images.githubusercontent.com/85088636/167277917-fd79782a-d931-49eb-99f2-9497376add30.png">

We will be working with six related tables, which contain eCommerce data about:

- Website Activity
- Products
- Orders and Refunds
- We'll use MySQL to understand how customers access and interact with the site, analyze landing page performance and conversion, and explore product-level sales.

- Scale of the database: 6 related tables, which contain more than 1,735,000 rows in total.

## Files

- [ ] create_mavenfuzzyfactory_vApril2022.sql : create the tables and insert the data
- [ ] preparing_workbench_vApril2022.sql :

* 1. adjusting max packet size to allow large files to run

* 2. adjusting SQL mode to allow invalid dates and use a smarter GROUP BY setting

* 3. adjusting timeout settings to run longer queries

- [ ] Traffic_Source_Analysis.sql : Queries to get,

* 1. monthly trends for gsearch sessions and orders

* 2. splitting out nonbrand and brand campaigns

* 3. monthly sessions and orders split by device type of nonbrand on Gsearch

* 4. monthly trends for Gsearch and each of other channels (bsearch, organic_search, and direct_type_in)

* 5. session to order conversion rates, by month

* 6. increase in CVR from the test (Jun 19 – Jul 28), and use nonbrand sessions and revenue since then to calculate incremental value

* 7. Show a full conversion funnel from each of the two different landing pages to orders (Jun 19 – Jul 28)

* 8. analyze the lift generated from the test (Sep 10 – Nov 10), in terms of revenue per billing page session, and the number of billing page sessions for the past month to understand monthly impact.

- [ ] Conversion_rate_and_margin_analysis.sql : Queries to get,

* 1. overall volume growth of the website sessions and orders by quarter

* 2. session-to-order conversion rate, revenue per order and revenue per session by quarter

* 3. quarterly view of orders from Gsearch nonbrand, Bsearch nonbrand, brand search overall, organic search, and direct type-in

* 4. overall session-to-order conversion rate trends for those same channels, by quarter

* 5. monthly trending for revenue and margin by product, along with total sales and revenue

* 6. monthly sessions to the /products page (sessions_to_product_page), and show how the % of those sessions clicking through another page has changed over time (clicked_to_next_page, clickthrough_rt), along with a view of how conversion from /products to placing an order has improved (products_to_order_rt)

* 7. sales data since Dec 05, 2014 (4th product available as a primary product, which was previously only a cross-sell item), and show each product cross-sells from one another

---



```
cd existing_repo
git remote add origin https://gitlab.com/devopscaptain_kong/sql-ecommence-website-data-analysis.git
git branch -M main
git push -uf origin main
```
