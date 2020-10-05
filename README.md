# Customer-Behavior-Analysis
## Executive Summary:
Siemens is a multinational conglomerate company involved in various industries. The project serves to analyze online customers’ visiting behavior through Amazon Web Service. By analyzing customers’ behavioral patterns and calculating statistics such as page conversion rate and top products of different regions, this project aims to facilitate further business decisions for the top management.
## Architecture
![alt](https://github.com/HeyQizhen/Customer-Behavior-Analysis/blob/main/architecture.jpg)
## Data flow
- Siemens sends us the data every morning in our Shared S3 Bucket.
- The Data Pipeline kicks in at 1:00 pm.
- The data first gets copied and lands in a Private S3 Bucket.
- Then, the Spark jobs starts off and does the transformation to load the data in Glue Table.
- Finally, the data is inserted into Redshift table from Glue Table.
## Data Description
user_info:
user_id, username, name, age, profession, city, gender
user_visit_action:
date, user_id, session_id, page_id, action_time, search_keyword, click_category_id, click_product_id, order_category_ids, order_product_ids, pay_category_ids, pay_product_ids, city_id
product_info:
product_id, product_name, extend_info
