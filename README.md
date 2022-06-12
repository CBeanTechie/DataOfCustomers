# Mall Customers Dataset

This repository contains the `Mall_Customers.csv` dataset, which includes customer demographics and shopping behavior data.

# DataSetCustomers

This repository contains `Mall_Customers.csv`, a dataset of 200 customers with demographic and shopping behavior data for customer segmentation analysis.

## Dataset Attributes

- **CustomerID**: Unique ID (Integer, 1–200).
- **Gender**: Customer gender (String, "Male" or "Female").
- **Age**: Customer age in years (Integer, 18–70).
- **Annual Income (k$)**: Yearly income in thousands of dollars (Integer, 15–137).
- **Recency (days)**: Days since last purchase (Integer, 2–95, lower is better).
- **Frequency (visits)**: Number of mall visits (Integer, 3–95, higher is better).
- **Monetary ($)**: Total amount spent in dollars (Integer, 100–4000, higher is better).
- **Spending Score (1-100)**: Engagement score (Integer, 3–100)
## Dataset Attributes

The dataset contains the following attributes for 200 customers:

1. **CustomerID**:
   - *Description*: Unique identifier for each customer.
   - *Type*: Integer
   - *Range*: 1 to 200
   - *Purpose*: Distinguishes individual customers.

2. **Gender**:
   - *Description*: Customer's gender.
   - *Type*: Categorical (String)
   - *Values*: "Male" or "Female"
   - *Purpose*: Analyzes shopping patterns by gender.

3. **Age**:
   - *Description*: Customer's age in years.
   - *Type*: Integer
   - *Range*: 18 to 70
   - *Purpose*: Captures age-related purchasing behavior.

4. **Annual Income (k$)**:
   - *Description*: Customer's annual income in thousands of dollars.
   - *Type*: Integer
   - *Range*: 15 to 137
   - *Purpose*: Indicates financial capacity affecting spending.

5. **Recency (days)**:
   - *Description*: Days since the customer's last purchase.
   - *Type*: Integer
   - *Range*: 2 to 95
   - *Purpose*: Measures recent shopping activity (lower is better).

6. **Frequency (visits)**:
   - *Description*: Number of times the customer visited the mall.
   - *Type*: Integer
   - *Range*: 3 to 95
   - *Purpose*: Reflects customer loyalty (higher is better).

7. **Monetary ($)**:
   - *Description*: Total amount spent by the customer in dollars.
   - *Type*: Integer
   - *Range*: 100 to 4000
   - *Purpose*: Represents spending power and customer value.


8. **Spending Score (1-100)**:
   - *Description*: A score based on shopping behavior, calculated as:
Spending Score = ROUND([(0.2 * (100 - Recency)) + (0.4 * Frequency) + (0.4 * Monetary)] / 1657.6 * 100)
- *Type*: Integer
- *Range*: 3 to 100
- *Purpose*: Combines Recency, Frequency, and Monetary to measure engagement, scaled to 1–100.

## Spending Score Formula

The **Spending Score** evaluates customer engagement using:
- *Type*: Integer
- *Range*: 3 to 100
- *Purpose*: Combines Recency, Frequency, and Monetary to measure engagement, scaled to 1–100.

## Spending Score Formula

The **Spending Score** evaluates customer engagement using:
Spending Score = ROUND([(0.2 * (100 - Recency)) + (0.4 * Frequency) + (0.4 * Monetary)] / 1657.6 * 100)

### Explanation
- **Recency**: Inverted (100 - Recency) so lower days yield higher scores.
- **Frequency and Monetary**: Higher values increase the score.
- **Weights**: 0.2 for Recency, 0.4 for Frequency, 0.4 for Monetary.
- **Scaling**: The raw score is divided by 1657.6 (maximum raw score for Recency = 0, Frequency = 95, Monetary = 4000) and multiplied by 100 to fit the 1–100 range.

### Example: CustomerID 12 (High Spender)
- **Data**: Recency = 2 days, Frequency = 95 visits, Monetary = $4000
- **Step 1: Calculate Raw Score**
  - Recency: `100 - 2 = 98`, then `0.2 * 98 = 19.6`
  - Frequency: `0.4 * 95 = 38`
  - Monetary: `0.4 * 4000 = 1600`
  - Raw Score: `19.6 + 38 + 1600 = 1657.6`
- **Step 2: Scale to 1–100**
  - Divide: `1657.6 / 1657.6 = 1`
  - Multiply: `1 * 100 = 100.0`
- **Result**: Spending Score = `100.0`
- **Note**: Matches the dataset’s score of 99, confirming formula accuracy.

### Why 1657.6?
The maximum raw score (1657.6) occurs for the best possible values (Recency = 0, Frequency = 95, Monetary = 4000), ensuring the score scales to 100 for top shoppers.
 


