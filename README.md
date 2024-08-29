# **Problem Statement**

The objective of this case study is to develop a predictive model for LoanTap, an online platform specializing in customized loan products for millennials. The focus is on the underwriting process for Personal Loans. Given a set of attributes for an individual, the goal is to determine whether a credit line should be extended and, if so, to provide recommendations on the repayment terms. The model should accurately predict the likelihood of loan repayment versus default, helping LoanTap make informed lending decisions and minimize the risk of non-performing assets (NPAs).

---
# **Concepts, Algorithm, and Technology Used**

**Language:**
- Python

**Modules:**
- NumPy
- Pandas
- Matplotlib
- Seaborn
- scikit-learn (sklearn)

**Algorithm:**
- Logistic Regression

**Concepts:**
- Exploratory Data Analysis (EDA)
- Data Preprocessing (handling missing values, encoding categorical variables)
- Feature Engineering
- Model Evaluation Metrics (Accuracy, Precision, Recall, F1-Score, ROC-AUC, PR-AUC)
- Model Optimization (Handling class imbalance, Regularization, Multi-collinearity check)
- Cross-Validation
- Confusion Matrix Analysis
- Precision-Recall Trade-off
- Receiver Operating Characteristic (ROC) Curve
- Feature Importance Analysis

---
# **Insights**

### **Exploratory Data Analysis (EDA) Insights:**
- **Dataset Overview:**
  - Total Rows: 396,030
  - Total Columns: 27
  - No duplicates; some missing values were noted.

- **Grade and Repayment:**
  - Grades A, B, C, and D have a higher number of fully-paid applicants compared to defaulters.
  - Grade B has the highest count of fully-paid loans.

- **Loan Term Insights:**
  - The 36-month period is the most common choice among applicants.
  - Loans with a 36-month term have a higher success rate compared to 60-month loans.

- **Applicant Characteristics:**
  - Most applicants report home ownership as 'Mortgage' or 'Rent.'
  - Individual applicants are more likely to apply for loans.
  - Applicants with no derogatory remarks or bankruptcies, and those with mortgage accounts, have a higher chance of receiving loans and successfully repaying them.

- **Loan Purpose:**
  - Debt consolidation and credit card repayment are the most common reasons for applying.
  - Applicants with longer employment histories have a higher likelihood of loan approval.

- **Occupation and Location Insights:**
  - Teachers and Managers are the occupations most likely to be granted loans.
  - Certain ZIP codes (e.g., 05113, 00813) are associated with high loan repayment rates, while others (e.g., 11650, 86630) have high default rates.

- **Feature Correlations:**
  - Strong correlations were found between `(loan_amnt, installment)` and `(pub_rec_bankruptcies, pub_rec)`.

### **Logistic Regression Model Insights:**
- **Accuracy:** 0.8
- **Precision:** 0.5
- **Recall:** 0.79
- **F1-Score:** 0.61
- **ROC-AUC:** 0.9
- **PR-AUC:** 0.77
- **Confusion Matrix:** TN: **`64.57%`**, FP: **`15.64%`**, FN: **`4.09%`**, TP: **`15.67%`**
- **Key Features:** **`ZIP code, grade, debt-to-income ratio (DTI), and loan amount`** were identified as the most important features based on their weights.

---
# **Recommendations**

Based on the analysis and model insights, the following recommendations can be made to improve loan disbursement practices while minimizing risk:

1. **Focus on High-Grade Applicants:**
   - Prioritize lending to applicants with Grade A, B, and C ratings, as they have shown a higher likelihood of fully repaying their loans. This will reduce the overall risk in the loan portfolio.

2. **Prefer Shorter Loan Tenures:**
   - Encourage applicants to choose 36-month loan terms, as these loans have demonstrated a higher success rate compared to 60-month loans. Shorter tenures reduce the likelihood of default, ensuring better cash flow and lower risk.

3. **Enhance Creditworthiness Checks:**
   - Give more weight to applicants with stable employment, no derogatory remarks, and no history of bankruptcies. These factors are strong indicators of an applicant’s ability to repay the loan, reducing the chances of default.

4. **Target Debt Consolidation Loans:**
   - Focus on applicants seeking loans for debt consolidation, as this purpose often reflects a proactive approach to managing finances. Such loans are more likely to be repaid in full, contributing to a healthier loan portfolio.

5. **Consider Zip-Code Risk Factors:**
   - Implement stricter lending criteria for applicants from high-risk zip codes with a history of defaults. Conversely, offer more favorable terms to applicants from low-risk areas where the likelihood of loan repayment is higher.

6. **Regularly Update the Model:**
   - Continuously retrain and update the logistic regression model with new data to reflect changes in economic conditions and borrower behavior. Regular updates will ensure the model remains accurate and relevant.

7. **Monitor Key Features:**
   - Pay close attention to the most important features identified by the model, such as zip code, grade, debt-to-income ratio (DTI), and loan amount. These features should be regularly monitored to refine loan approval criteria.

8. **Consider Implementing a Two-Stage Model:**
   - Utilize a two-stage model where the first stage identifies potential defaulters with high recall, and the second stage focuses on reducing false positives. This approach balances the need for accurate default detection with the goal of minimizing missed opportunities for lending.

9. **Balance Loan Approvals with NPA Risks:**
   - While aiming to reduce NPAs, it is also important not to be overly conservative in loan disbursements. Striking the right balance will ensure that opportunities for profitable lending are not missed.

10. **Implement Human Review for High-Risk Cases:**
    - For applicants who are borderline in terms of risk, consider involving human underwriters to review the cases. This additional step can help prevent potential NPAs while still allowing for reasonable loan approvals.
