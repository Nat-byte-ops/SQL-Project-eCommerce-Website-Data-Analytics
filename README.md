# SQL-Project-eCommerce-Database-Analysis

Background:
This is an eCommerce Database Analytics Project for Maven Fuzzy Factory (fake name), an online retailer which has just launched their first product. 

Stakeholders:
As a member of the startup team, I will work with the CEO, the Head of Marketing, and the Website Manager to help steer the business.

Goals:
Using SQL to:
* Access and explore the company's database
* Become the data expert for the company, and the go-to person for mission critical analyses
* Analyze and optimize the business' marketing channels, measure and test website conversion performance, and use data to understand the impact of new product launches



Overview of the Company Database
<img width="765" alt="Screen Shot 2022-05-08 at 11 22 37 am" src="https://user-images.githubusercontent.com/85088636/167277917-fd79782a-d931-49eb-99f2-9497376add30.png">

We will be working with six related tables, which contain eCommerce data about:
* Website Activity
* Products
* Orders and Refunds
* We'll use MySQL to understand how customers access and interact with the site, analyze landing page performance and conversion, and explore product-level sales.


1. Traffic Source Analysis
* Traffic source analysis is about understanding where your customers are coming from and which channels (email, social media, search, or direct, etc) are driving the highest quality traffic (calculate the conversion rate).
* We use the utm parameters stored in the database to identify paid website sessions
* From our session data, we can link to our order data to understand how much revenue our paid campaigns are driving
