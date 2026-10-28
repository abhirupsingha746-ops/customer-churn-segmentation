# Customer Churn Segmentation and Recommendation Model

## 1. Project Objective

The objective of this project is to analyze customer data, identify customer segments, understand observed churn patterns, and recommend suitable customer retention actions.

## 2. Dataset Overview

The dataset contains 15 customer records. It was used to explore customer tenure, support tickets, contract types, and churn status.

## 3. Feature Selection

The analysis uses the following features:

* **Tenure:** The length of time a customer has stayed with the company.
* **Support Tickets:** The number of support requests raised by a customer.
* **Contract Type:** The type of subscription contract.
* **Churn Status:** Whether a customer has left the service.

These features help describe customer behavior and support the rule-based risk assessment.

## 4. Customer Segmentation

Customers were divided into three segments based on tenure:

* **New Customers:** Tenure below 12 months.
* **Established Customers:** Tenure from 12 to 24 months.
* **Long-Term Customers:** Tenure above 24 months.

## 5. Churn Analysis

The observed churn results are summarized below.

| Customer Segment      | Total Customers | Churned Customers | Observed Churn Rate |
| --------------------- | --------------: | ----------------: | ------------------: |
| New Customers         |               5 |                 5 |                100% |
| Established Customers |               6 |                 2 |              33.33% |
| Long-Term Customers   |               4 |                 0 |                  0% |
| **Total**             |          **15** |             **7** |          **46.67%** |

New customers had the highest observed churn rate in this small dataset. Long-term customers had no observed churn in the available records.

## 6. Rule-Based Churn-Risk Score

A transparent rule-based scoring system was used to prioritize customers who may need retention support.

| Condition                                  | Points |
| ------------------------------------------ | -----: |
| Tenure below 12 months                     |    +30 |
| Support tickets greater than or equal to 4 |    +40 |
| Month-to-Month contract                    |    +30 |

Risk categories:

* **Low Risk:** 0–29 points.
* **Medium Risk:** 30–59 points.
* **High Risk:** 60–100 points.

The score is a manually defined prioritization tool. It is not a statistically validated probability of future churn.

## 7. Validation and Edge-Case Testing

The scoring rules should be tested against customers who meet one, two, or all three conditions, as well as customers who meet none of them.

The implementation should also check missing values, unexpected contract types, and tenure values at segment boundaries. Record the actual test results in the analysis notebook.

## 8. Customer Retention Recommendations

### New Customers

* Improve onboarding and explain the service clearly.
* Contact customers early to identify difficulties.
* Monitor early support requests and customer feedback.

### Established Customers

* Review frequent support requests and unresolved issues.
* Collect feedback from customers who have churned.
* Offer relevant assistance based on customer needs.

### Long-Term Customers

* Monitor customer satisfaction.
* Review whether the current plan still meets customer needs.
* Encourage feedback and recognize customer loyalty.

### High-Risk Customers

* Prioritize outreach to customers with higher rule-based scores.
* Investigate their support history and contract needs.
* Track whether retention actions improve customer outcomes.

## 9. Limitations

This analysis is based on only 15 customer records. Therefore, the results may not represent the wider customer population.

The rule-based score uses manually assigned points and has not been statistically calibrated or validated as a prediction model. Observed churn rates describe this dataset only and should not be interpreted as guaranteed future outcomes.

## 10. Conclusion

This project demonstrates how customer segmentation, observed churn analysis, transparent risk scoring, and targeted retention recommendations can be combined into a simple customer analytics workflow.

With a larger dataset and further validation, the analysis could be improved by testing additional behavioral features and evaluating whether the scoring rules help identify customers who subsequently churn.
