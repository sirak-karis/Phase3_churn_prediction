# SyriaTel Churn Prediction - Non-Technical Presentation

Presenter: Joanne Kariuki
Stakeholder: SyriaTel Shareholders and Business Team


## Project Overview
I analysed the the customer churn of SyriaTel using data_driven insights with the aim of reducing the customer churn as it leads to substantail revenue losses. I used macine learning to identify patterns in customer behaviour and build predictive models which in turn helped targeted actions to retain high-risk customers

## Project Goals
- **Examined** Customer behavior and service usage patterns from the dataset to understand key indicators of churn.  
- **Identified** The most influential features contributing to customer churn, such as frequent customer service interactions. 
- **Recommended** Strategic actions to proactively retain high-risk customers.

## Why This Project Matters
- **Competitive Landscape:** The telecom industry in Syria is competitive, with customers easily switching providers due to minimal switching costs and similar pricing.
- **High Stakes:** Losing a customer costs more than retaining one. Customer churn not only results in immediate revenue loss but also undermines brand loyalty and market share. 
- **Opportunity:** By predicting churn before it happens, SyriaTel can proactively intervene, personalize retention strategies, and significantly reduce long-term losses.

## Business Understanding

### Stakeholder
- **Primary Stakeholder:** Shareholders and Business Tean
  - **Role:** The business team oversees customer retention, gain and service optimization  
  - **Interest:** find ways to identify customers at risk of leaving and reduce churn-related revenue loss.

### Business Questions
1. Can we identify which customers are likely to churn before they do?

2. What customer behaviors and attributes are most associated with churn?

3. How well can we predict churn using historical data?



## Data Understanding

### Data Sources

2. **(https://www.kaggle.com/datasets/becksddf/churn-in-telecoms-dataset/code)**
   - **File:** `bigml_59c28831336c6604c800002a.csv`  

  
   - **Dataset Overview:**
3,333 customer records from SyriaTel, each with multiple service and usage features.

   - **Target Variable:**
Churn – whether the customer left the service (Yes or No).

   - **Key Features Include:**

Service Usage:
Day, evening, night, and international call minutes and their charges.

Service Plans:
Whether the customer is subscribed to an International Plan or Voice Mail Plan.

Customer Support Interactions:
Number of times the customer called customer service.
     


## Data Limitations
- **No Customer Demographics:**
The dataset lacks information like age, income, or location, which could offer deeper behavioral insights.

- **Plan Details are Simplified:**
Plans are labeled as “Yes/No” without details on pricing, usage limits, or customer preferences.

- **Assumption of Churn Definition:**
Churn is binary (Yes/No), but in reality, customer disengagement can be gradual or reversible.


## Data Preparation Strategy

### Cleaning
- **Handling Missing Values:**  
  - No missing values were found in the dataset. All rows were retained.
- **Target Variable Encoding:**  
  - The target column Churn was originally categorical (Yes, No).

We converted it to binary format:Yes → 1 (churned) and No → 0 (retained)
- **Categorical Feature Encoding:**  
  - Two features were binary categorical (International Plan and Voice Mail Plan).

These were also encoded to Yes → 1, No → 0
No one-hot encoding was needed as there were no multi-class categorical columns
- **Feature Scaling:**
  - Logistic Regression is sensitive to the scale of input features.
I applied StandardScaler from sklearn.preprocessing to all numerical features:
Call minutes, Charges, Number of calls and Account length
- **Train-Test Split:**
  - Data was split using train_test_split() from sklearn.model_selection:
80% training / 20% testing

Stratified sampling was used to maintain the same churn rate distribution across both sets.


## Modelling Strategy
