# SQL-Project-eCommerce-Database-Analysis

## Background:
This is an eCommerce Database Analytics Project for Maven Fuzzy Factory (fake name), an online retailer which has just launched their first product. 

## Stakeholders:
As a member of the startup team, I will work with the CEO, the Head of Marketing, and the Website Manager to help steer the business.

## Goals:
Using SQL to:
* Access and explore the company's database
* Become the data expert for the company, and the go-to person for mission critical analyses
* Analyze and optimize the business' marketing channels, measure and test website conversion performance, and use data to understand the impact of new product launches



## Overview of the Company Database
<img width="765" alt="Screen Shot 2022-05-08 at 11 22 37 am" src="https://user-images.githubusercontent.com/85088636/167277917-fd79782a-d931-49eb-99f2-9497376add30.png">

We will be working with six related tables, which contain eCommerce data about:
* Website Activity
* Products
* Orders and Refunds
* We'll use MySQL to understand how customers access and interact with the site, analyze landing page performance and conversion, and explore product-level sales.


## 1. Traffic Source Analysis
* Traffic source analysis is about understanding where your customers are coming from and which channels (email, social media, search, or direct, etc) are driving the highest quality traffic (calculate the conversion rate).
* We use the utm parameters stored in the database to identify paid website sessions
* From our session data, we can link to our order data to understand how much revenue our paid campaigns are driving

### 1.1 Request from CEO: A breakdown by UTM source, campaign and referring domain to understand where the bulk of our website sessions are coming from until April 12, 2012
* Solution Query:

![Screen Shot 2022-05-09 at 5 24 31 pm](https://user-images.githubusercontent.com/85088636/167360645-e1c81179-f0d9-4a05-8daf-c032737846bd.png)
* Result Grid

![Screen Shot 2022-05-09 at 5 33 22 pm](https://user-images.githubusercontent.com/85088636/167361987-fa840cf3-d96d-4a86-a538-d9d7e23c7e05.png)

### 1.2 Drill deeper into gsearch nonbrand campaign traffic to explore potential optimization opportunities
* According to 1.1, it seems that gsearch nonbrand is the company's major traffic source, but we need to understand if those sessions are driving sales
* So we'll calculate the conversion rate (CVR) from session to order 
* After discussing with the Marketing Director, we know that based on what we're paying for clicks, we'll need a CVR of at least 4% to make the numbers work
* If we're much lower, we'll need to reduce bids
* If we're higher, we can increase bids to drive more volumne

* Solution Query:

![Screen Shot 2022-05-09 at 7 11 53 pm](https://user-images.githubusercontent.com/85088636/167378792-9186c48c-9099-4a58-8a30-dd4022af1179.png)

* Result Grid

![Screen Shot 2022-05-09 at 7 13 13 pm](https://user-images.githubusercontent.com/85088636/167378988-3243fa0e-7409-41ca-ad16-b67fc0379205.png)

### 1.3 Bid Optimization
* Analyzing for bid optimization is about understanding the value of various segments of paid traffic, so that one can optimize the marketing budget

![Screen Shot 2022-05-09 at 7 26 44 pm](https://user-images.githubusercontent.com/85088636/167381499-be2586fe-6c83-4369-8c61-df6583095d8d.png)
  * Using conversion rate and revenue per click analyses to figure out how much you should spend per click to acquire customers
  * Understanding how your website and products perform for various subsegments of traffic (i.e. mobile vs desktop) to optimize within channels
  * Analyzing the impact that bid changes have on your ranking in the auctions, and the volume of customers driven to your site

* According to the result from 1.2, it looks like we're below the 4% threshold we need to make the economics work.
* Based on this analysis, we'll need to dial down our search bids a bit since we're over-spending based on the current conversion rate
* In this part, we'll monitor the impact of bid reductions
* And analyze performance trending by device type in order to refine bidding strategy


* So we bid down gsearch nonbrand on 2012-04-15, the Marketing Director asked to pull gsearch nonbrand trended session volume by week, to see if the bid changes have caused volume to drop at all
* Solution Query

![Screen Shot 2022-05-10 at 9 43 02 pm](https://user-images.githubusercontent.com/85088636/167620690-9ccf98e9-9122-49e2-ac86-d103ba6b26d4.png)

* Result Grid

![Screen Shot 2022-05-10 at 9 43 37 pm](https://user-images.githubusercontent.com/85088636/167620766-faab7f15-ece0-4a80-b8fb-e90076df145f.png)

### 1.4 Traffic Source Trending
* Based on 1.3 result, it does look like gsearch nonbrand is fairly sensitive to bid changes
* The ultimate goal is maximun volume, but also maintain some level of efficiency
* So we'll continue to monitor volume levels
* Think about how we could make the campaigns more efficient so that we can increase volumn again
* First of all, we tried to pull conversion rates from session to order by device type to see if desktop performance is better than on mobile. If so, we may be able to bid up for desktop specifically to get more volumn
* Solution Query

![Screen Shot 2022-05-10 at 10 18 31 pm](https://user-images.githubusercontent.com/85088636/167626493-603057a9-79f6-4b15-9712-86803c876799.png)

* Result Grid

![Screen Shot 2022-05-10 at 10 19 02 pm](https://user-images.githubusercontent.com/85088636/167626584-531f39dc-dca6-4833-aafc-0bbb5319fb00.png)

### 1.5 Traffic Source Bid Optimization - segment trending
* From 1.4, we can see that the conversion rate for desktop traffic is about 3.7%, for mobile traffic, it's less than 1% 
* So the Marketing Team bid the gsearch nonbrand desktop campaigns up on 2012-05-19 and asked the data team to pull weekly trends for both desktop and mobile so they can see the impact on volume, and 2012-04-15 until the bid change can be used as a baseline
* Solution Query
![Screen Shot 2022-05-11 at 2 16 09 pm](https://user-images.githubusercontent.com/85088636/167768035-4ccfbb5b-a402-4265-bab0-8f61bdf677e5.png)
* Result Grid
![Screen Shot 2022-05-11 at 2 16 40 pm](https://user-images.githubusercontent.com/85088636/167768072-4eaec1c3-ccaf-4eef-b6e5-5855272d39e0.png)

* Based on the above result, we can see that mobile has been pretty flat or a little down, but desktop is looking strong thanks to the bid changes we made based on the previous conversion analysis
* Next, we'll continue to monitor device-level volume and be aware of the impact bid levels has
* And continue to monitor conversion performance at the device-level to optimize spend

## 2. Analyzing Website Performance
* In this section, we'll dive deeper into the company's website with the Website Manager (Front End) to understand where customers are landing on the website and how they make their way through the conversion funnel on the path to placing an order
 
### 2.1 Analyzing Top Website Pages & Entry Pages
* Website content analysis is about understanding which pages are seen the most by your users, to identify where to focus on improving your business
![Screen Shot 2022-05-11 at 2 32 28 pm](https://user-images.githubusercontent.com/85088636/167769614-903798b3-8e7e-4840-bc72-d78de19aa321.png)
Common Use Cases:
* Finding the most-viewed pages that customers view on your site
* Identifying the most common entry pages to your website - the first thing a user sees
* For most-viewed pages and most common entry pages, understanding how those pages perform for your business objectives
#### 2.1.1 Identifying Top Website Pages
* The Website Manager would like to pull the most-viewed website pages, ranked by session volume
* Solution Query

![Screen Shot 2022-05-11 at 4 26 54 pm](https://user-images.githubusercontent.com/85088636/167782778-1c023391-e855-4cba-809e-f282706846e3.png)

* Result Grid

![Screen Shot 2022-05-11 at 4 27 20 pm](https://user-images.githubusercontent.com/85088636/167782840-66fc20c6-40c3-4a4c-a43c-33e9baa6ac53.png)

* According to the above result, it definitely seems like the homepage, the products page and the Mr. Fuzzy page get the bulk of our traffic
* We'd like to dig into whether this list is also representative of our top entry pages
* And analyze the performance of each of our top pages to look for improvement opportunities

#### 2.1.2 Identifying Top Entry Pages
* To confirm where our users are hitting the site, we'll pull a list of the top entry pages
* First of all, we'll pull all entry pages and rank them on entry volume
