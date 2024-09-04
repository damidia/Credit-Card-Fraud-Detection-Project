# Credit Card Fraud Detection Project  
**Author:** Akhil Damidi  

This project uses the *Credit Card Transactions Fraud Detection Dataset* which contains credit card transactions made by 1,000 customers from January 2019 to December 2020. The dataset includes both legitimate and fraudulent transactions from a pool of 800 merchants. The primary objective of this project is to develop fraud detection models that can identify potentially fraudulent transactions while minimizing false positives.  

### Key Features:
- **cc_num**: Credit card number of the customer
- **merchant**: Merchant name
- **category**: Category of the merchant
- **amt**: Transaction amount
- **first**: First name of the credit card holder
- **last**: Last name of the credit card holder
- **gender**: Gender of the credit card holder
- **state**: State where the transaction took place
- **lat** and **long**: Location (latitude, longitude) of the cardholder
- **merch_lat** and **merch_long**: Location (latitude, longitude) of the merchant
- **is_fraud**: Binary label indicating whether the transaction is fraudulent (1) or not (0)

### Data Source:
The dataset was generated using the Sparkov Data Generation tool on GitHub, created by Brandon Harris. The simulation was run for the duration of January 1, 2019, to December 31, 2020, and the resulting files were combined into a standard format.  
[Dataset on Kaggle](https://www.kaggle.com/datasets/kartik2112/fraud-detection?select=fraudTrain.csv)

---

### Goal:
The goal of this project is to perform exploratory data analysis (EDA) and apply machine learning models to detect fraudulent credit card transactions. By understanding the patterns and behavior of fraudulent activities, we aim to improve fraud detection while reducing false positives.

---

### Results:
#### **Initial Model (Logistic Regression):**
Initially, I experimented with a Logistic Regression model using standard features such as transaction amount, merchant, and customer details. The model provided a strong baseline with a high recall (ability to identify frauds) but occasionally flagged legitimate transactions as fraudulent (false positives).

#### **Random Forest Model:**
I then implemented a Random Forest model, which achieved significant performance improvements. The key features contributing to fraud detection included:
1. **Distance from Home:** Transactions far from the cardholder's home location were more likely to be fraudulent.
2. **Transaction Amount:** Higher-than-usual transaction amounts were commonly associated with fraud.
3. **Merchant & Geographic Location:** Certain merchants and locations were more prone to fraudulent transactions.

This model significantly reduced false positives while maintaining high accuracy, demonstrating the Random Forest's ability to handle complex relationships in the dataset.

#### **Advanced Models (XGBoost and Neural Networks):**
Next, I applied more advanced models, such as XGBoost and Neural Networks. Both models performed exceptionally well, achieving perfect accuracy on the training data, though this indicated possible overfitting. Cross-validation helped confirm their effectiveness while providing more generalizable results.

### Top 3 Features:
1. **Distance from Home:** Geographic distance between the cardholder and merchant.
2. **Transaction Amount:** Higher transaction values were a key indicator of fraud.
3. **Merchant Information:** Certain merchants were more frequently associated with fraudulent transactions.

---

### Conclusion:
By exploring different machine learning techniques and focusing on key features like geographic distance and transaction amounts, this project successfully improved the accuracy of fraud detection while reducing false positives. The Random Forest model proved particularly useful in striking a balance between precision and recall, making it a reliable choice for real-world fraud detection systems.
