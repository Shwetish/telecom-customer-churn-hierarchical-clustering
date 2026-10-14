# telecom-customer-churn-hierarchical-clustering
Customer churn segmentation and behavioral pattern analysis on mixed categorical and numerical telecom data (Telco_customer_churn.xlsx) using hierarchical clustering.

# Telecom Customer Churn Segmentation using Hierarchical Clustering

## 1. Business Problem
### 1.1. Business Objective
To segment telecom customers using mixed data types (`Telco_customer_churn.xlsx`) to uncover underlying behavioral patterns and risk factors associated with customer churn. The insights help retention teams design targeted intervention programs.
### 1.2. Constraints
* Presence of both categorical contracts/services and numerical charges requires careful encoding and distance metric selection (e.g., Gower's distance or standard dummy encoding with Euclidean distance).
* High dimensionality may affect cluster compactness.

## 2. Data Dictionary
*(Note: Tailor based on dataset features)*
| Feature Name | Data Type | Description |
| --- | --- | --- |
| `CustomerID` | String | Unique customer identifier |
| `Tenure` | Numerical | Number of months the customer has stayed with the company |
| `Contract` | Categorical | Type of customer contract (Month-to-month, One year, Two year) |
| `MonthlyCharges` | Numerical | Amount charged to the customer monthly |
| `TotalCharges` | Numerical | Total amount charged to the customer |
| `Churn` | Binary/Categorical | Whether the customer churned or not (Yes/No) |

## 3. Data Pre-processing
* **Data Cleaning:** Handled missing values (e.g., in `TotalCharges`), removed redundant ID columns.
* **Feature Engineering & Encoding:** Converted categorical variables into numerical format using One-Hot Encoding (`pd.get_dummies`) or Label Encoding.
* **Normalization:** Scaled numerical features to bring them on par with encoded binary columns.

## 4. Exploratory Data Analysis (EDA)
* **Summary:** Churn rate percentages, average monthly spend, and tenure summary statistics.
* **Univariate Analysis:** Frequency bar charts for contract types and histograms for monthly charges.
* **Bivariate Analysis:** Cross-tabulations and stacked bar charts showing churn distribution across tenure brackets and contract types.

## 5. Model Building
* **5.1 Scaled Data:** Built hierarchical clustering models on preprocessed mixed feature space.
* **5.2 Dendrogram Visualization:** Created dendrograms to inspect natural cluster hierarchies.
* **5.3 Validation & Insights:** Evaluated cluster purity against the `Churn` target variable to isolate high-risk attrition groups.

## 6. Business Benefits & Impact
* Proactive retention campaigns for customer segments identified at high risk of churning.
* Tailored pricing and service plan recommendations to improve customer loyalty.
