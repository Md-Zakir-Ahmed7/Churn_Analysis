# Customer Churn Analysis

![Image](https://github.com/user-attachments/assets/b4ea425f-c542-471b-85e6-d63c6e04c097)

## Problem Statement:
The goal of this project is to analyze customer churn, which is the rate at which customers leave a business relative to the total customers. By studying the churn rate against various factors, we aim to identify the main contributors to churn and provide actionable insights for business users. These insights will help businesses strategize and make informed decisions to reduce churn.

## Dataset

The data for this project is a CSV file containing the following columns:

### Column	Description
- customer_id = Unique identifier for each customer

- credit_score = Credit score of the customer

- country = Country of the customer

- gender = Gender of the customer

- age =	Age of the customer

- tenure Duration (in years) = the customer has been with the company

- balance = Account balance of the customer

- products_number =	Number of products owned by the customer

- credit_card = Whether the customer owns a credit card (1 = Yes, 0 = No)

- active_member = Whether the customer is an active member (1 = Active, 0 = Inactive)

- estimated_salary = Estimated salary of the customer

- churn =  Whether the customer churned (1 = Yes, 0 = No)


## Data Collection and Preparation

### 1. Connect, Clean, and Transform Data:

1. Imported the dataset into Power Query.
2. Promoted the first row as headers.
3. Removed unnecessary columns (e.g., estimated_salary).
4. Renamed steps and columns for clarity.
5. Checked and updated data types.
6. Replaced binary values with meaningful labels:
7. Credit card: 1 → Owned, 0 → Not Owned.
8. Activity status: 1 → Active, 0 → Inactive.
9. Churn status: 1 → Churned, 0 → Not Churned.

### 2. Created Conditional Columns:

1. Age Group: Categorized ages into groups.
2. Credit Score Category: Classified credit scores.
3. Account Balance Category: Grouped balances.


## Data Modeling

### 1. Reference Tables:

1. Created a reference table for Age Group containing distinct values.
2. Created a reference query for Account Balance and removed duplicates.
3. Created a reference query for Credit Score and removed duplicates.

### 2.Model Relationships:

Set relationships with many-to-one and one-to-many cardinality in the model tab.

### 3.Created Measures:

1. Customers = COUNT('Bank Customer Data'[Customer ID])
2. Customers Lost = CALCULATE(COUNT('Bank Customer Data'[Churn Status]), 'Bank Customer Data'[Churn Status] = "Churned")
3. Churn Rate = 'Bank Customer Data'[Customers Lost] / 'Bank Customer Data'[Customers]


## Visualizations
#### 1. Donut Charts:

- Customers by activity status, credit card status, country, and product ownership.

#### 2. Line and Clustered Column Charts:

- Customers by age group vs. churn rate.
- Customers by credit score vs. churn rate.
- Customers by account balance vs. churn rate.

#### 3. Slicers:

- Added slicers for filtering churn status.

#### 4. Gauge Chart:

- Showed churn rate with maximum, minimum, and target rates.

#### 5. KPI:

- Show Total Customers.

#### Snapshot of Not Churned Dashboard

![Image](https://github.com/user-attachments/assets/b290778b-1736-4c61-b185-6d9e636b4b4c)


#### Snapshot of Churn Analysis by Female Dashboard

![Image](https://github.com/user-attachments/assets/289f6f9a-9558-43ec-abf7-e63dcff175cc)



## Insights and Findings
### Customer Segmentation

1. Gender:
- Distribution: Male and female customers are nearly equally distributed (45%-55%).
- Churn Behavior: No significant difference in churn rates between genders.

2. Activity Status:
- Active Customers: Constitute 51-55% of the base, with lower churn rates.
- Inactive Customers: Show a higher propensity to churn, indicating an opportunity for re-engagement strategies.

3. Credit Card Ownership:
- With Credit Cards: Majority of customers (~70-75%) own credit cards.
- Without Credit Cards: Display higher churn rates, potentially due to reduced loyalty.

4. Region:
- Country Distribution: Customers are evenly distributed across France, Germany, and Spain.
- Churn Trend: Spain exhibits slightly higher churn rates compared to other regions.

5. Products:
- Preferred Products: Product 1 and Product 2 are most popular (~45-55% adoption).
- Product 3: Has the lowest adoption rate (<3%) and correlates with higher churn.


###  Behavioral Insights

1. Age Groups:
- Major Segment: Customers aged 41-50 form the largest group but have the highest churn rates.
- Lower Churn Groups: Younger customers (21-30) and older customers (61+) are less likely to churn.

2. Credit Scores:
- High-Risk Segment: Customers with credit scores below 600 are most likely to churn.
- Low-Risk Segment: Customers with scores above 800 exhibit the lowest churn rates.

3. Account Balance:
- High Churn Range: Customers with account balances between 100K-200K churn the most.
- Low Churn Range: Balances below 10K or above 200K have significantly lower churn.


## Recommendations

#### Focus on High-Churn Segments:

- Develop targeted retention strategies for inactive customers, customers with low credit scores (<600), and those in the mid-tier account balance range (100K-200K).

#### Region-Specific Strategies:

- Address Spain's slightly higher churn rate with localized incentives and loyalty programs.

#### Product Strategy:

- Investigate why Product 3 has low adoption and higher churn, and make necessary improvements.

#### Tailored Engagement:

- Design age-specific campaigns to engage customers aged 41-50, as they have the highest churn rate.

#### Credit Score Programs:

- Offer financial products or benefits to customers with low credit scores to improve retention.



#### Snap of Dashboard

![Image](https://github.com/user-attachments/assets/b4ea425f-c542-471b-85e6-d63c6e04c097)
