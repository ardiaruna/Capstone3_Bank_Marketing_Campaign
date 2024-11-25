# Capstone3_Bank_Marketing_Campaign
### **Business Context**
A Term deposit is a deposit that a bank or a financial institurion offers with a fixed rate (often better than just opening deposit account) in which your money will be returned back at a specific maturity time.

Term deposits are a crucial product for banks, offering a secure investment option for customers while providing a steady source of funds for the bank’s lending and operational activities. However, promoting term deposits requires a nuanced approach, as customers have varying financial needs, risk appetites, and savings preferences. With increasing competition in the financial industry, banks need to employ data-driven strategies to effectively target the right customers and maximize the return on their marketing investments.

### **Business Problem**

Marketing campaigns for term deposits often face low conversion rates due to inefficient targeting. Blanket marketing approaches lead to wasted resources, customer disengagement, and missed opportunities to convert high-potential leads. The challenge lies in identifying customers most likely to subscribe to a term deposit and designing targeted campaigns that appeal to their specific financial behaviors and preferences.

### **Business Goal**
The goal is to develop a machine learning model that predicts the likelihood of a customer subscribing to a term deposit account 

### **Metric Evaluation**
Our primary focus is on customer who deposit, so we will assign the target as such:
- 1: Customer who deposit
- 0: Customer who doesn't deposit

`Type 1 Error`    : False Positive (customer who are predicted to subscribe to a term deposit but actually doesn't subscribe) <br>
Consequence     : Marketing Campaign Inefficiency, Wasted Resources, Customer Dissatisfaction <br>

`Type 2 Error`    : False Negative (customer who are predicted to not subscribe to a term deposit but actually does subscribe)<br>
Consequence     : Reduced Customer Engagement

I will use **Precision** for our evaluation metric, because **Precision** aims to minimize **type 1 error**, therefore increasing the efficiency of the marketing campaign and less wasted resource.

To give a perspective on why precision are important, here are case example: <br>

**Assumptions**:
- Amount of customer = 10000
    - customer who subscribe to a term deposit = 4000
    - customer who doesn't subscribe to a term deposit = 6000
- Minimum amount to deposit = $5000 ([Source](https://www.commbank.com.au/banking/term-deposits.html))
- Assuming all the customer who subscribe to a term deposit are all for 12 Months; the interest rate will be = 4.35% ([Source](https://www.commbank.com.au/banking/term-deposits.html))
- Marketing campaign budget/cost based on revenue = 14% ([Source](https://hawksem.com/blog/what-percentage-of-revenue-should-be-spent-on-marketing/#:~:text=Average%20marketing%20budgets%20vary%20from,Banking%20%26%20finance%3A%2014%25))

**Calculations**:
- $\ \text{Revenue}     = \text{customer who subscribe to a term deposit * minimum amount to deposit * interest rate (12 month)}$<br>
$\   \text{Revenue}     = 4000 * 5000 * 0.0435= 870,000$

- $\ \text{Marketing budget/cost}   = \text{0.14 * Revenue}$ <br>
$\ \text{Marketing budget/cost}     = 0.14 * 870,000 = 121,800$

**Marketing budget/cost per Customer**: <br>

$\ \text{Marketing budget/cost per Customer} = \frac{\text{Marketing budget/cost}}{\text{Amount of customer}}$ <br>

$\ \text{Marketing budget/cost per Customer} = \frac{121,800}{10,000} = {12.18}$

**Based on the case example**:

**Precision**:
- Precision is about reducing false positives (customers incorrectly predicted to subscribe but do not).
- Each false positive avoided saves the marketing cost per customer: $12.18.

- ### **nalytical Approach**
To address the problem and meet the campaign’s objectives, the following steps will be undertaken:

1. Data Understanding:
    - Collecting Data
    - Describing Data
    - Exploring Data (EDA)
2. Data Preparation:
    - Cleaning Data
    - Feature Engineering (if necessary)
3. Modelling
    - Preprocessing
    - Data Spliting
    - Model Benchmark
    - Hyperparameter Tuning
4. Evaluation
    - Final Result Comparison (Before and After Tuning)
    - Confusion Matrix
    - Feature Importace
    - SHAP

5. Conclusion and Recommendation

6. Deployment
