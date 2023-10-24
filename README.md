#### **Background**:
We are a small startup focusing mainly on providing machine learning solutions in the European banking market. We work on a variety of problems including fraud detection, sentiment classification and customer intention prediction and classification.

We are interested in developing a robust machine learning system that leverages information coming from call center data.

Ultimately, we are looking for ways to improve the success rate for calls made to customers for any product that our clients offer. Towards this goal we are working on designing an ever evolving machine learning product that offers high success outcomes while offering interpretability for our clients to make informed decisions.

#### **Data Dictionary**:
The data comes from direct marketing efforts of a European banking institution. The marketing campaign involves making a phone call to a customer, often multiple times to ensure a product subscription, in this case a term deposit. Term deposits are usually short-term deposits with maturities ranging from one month to a few years. The customer must understand when buying a term deposit that they can withdraw their funds only after the term ends. All customer information that might reveal personal information is removed due to privacy concerns.

Attributes:

Age : age of customer (numeric)

Job : type of job (categorical)

Marital : marital status (categorical)

Education (categorical)

Default: has credit in default? (binary)

Balance: average yearly balance, in euros (numeric)

Housing: has a housing loan? (binary)

Loan: has personal loan? (binary)

Contact: contact communication type (categorical)

Day: last contact day of the month (numeric)

Month: last contact month of year (categorical)

Duration: last contact duration, in seconds (numeric)

Campaign: number of contacts performed during this campaign and for this client (numeric, includes last contact)

Target(y) - has the client subscribed to a term deposit? (binary)


#### **Objective**:
*    Hit %81 or above accuracy by evaluating with 5-fold cross validation and reporting the average performance score.
*    We are also interested in finding customers who are more likely to buy the investment product. Determine the segment(s) of customers our client should prioritize.
*   What makes the customers buy? Tell us which feature we should be focusing more on. 

####  **Project Overview**:
*  The main goal is to predict if the customer will subscribe to a term deposit or not. Most of the features are categorical and only few are numerical, we need to analyze them efficiently by fitting the best models with optimal hyperparameter values. We will be using cross validation techniques for better training.
*  Out of 40,000 people, only 7.5% subscribed to the term deposit marketing plan, with 37,104 individuals not subscribing, showing a significant class imbalance. Key findings from the cross-tabulation revealed that the majority of subscribed individuals hold jobs in the management field, have a background in secondary education, and are married.
*  After looking at the categorical features based on the target class, it showed a significant difference in the proportion between subscribed and non-subscribed individuals:
    ![propor](https://github.com/skreddypalvai/7MlWQpaQ38udIkNh---Apziva-Project/assets/137756791/c2e0129d-146e-4a0b-898e-0d178d3aaae2)
*  'Duration' shows a notably strong positive correlation(0.46) with the target class in contrast to numerical features such as age, balance, campaign, and day. It's important to note that correlation values only define linear relationships. Therefore, we should implement Tree-based models to capture non-linear relationships between the features and the target.
*  I used a box plot to show that there are noticeable outliers in the 'duration', 'campaign', and 'balance' features. I removed these outliers using winsorization technique. To address class imbalance, I applied sampling methods to bring the majority class down to 19000 and the minority class up to 5900.

#### **Key Results**:
##### **Logistic Regression**
*  The Logistic Regression model achieved an impressive 93% mean cross-validation accuracy and 93% ROC-AUC score. Given the imbalanced classes in our binary classification task, it's crucial to prioritize precision and recall metrics over other metrics. So, the model attained a avg precision score of 74%.
  ![propor](https://github.com/skreddypalvai/7MlWQpaQ38udIkNh---Apziva-Project/assets/137756791/db33192b-9c6b-489e-8eda-38d2026f071c)
![download (1)](https://github.com/skreddypalvai/7MlWQpaQ38udIkNh---Apziva-Project/assets/137756791/51f7adca-78c5-4a64-b9fc-bce55f256079)
##### **Random Forest**
*  The Random Forest model, fitted with the best hyperparameter values, achieved a 93% accuracy score and a 73% ROC-AUC score. It also had a high Recall score of 75% but a low Precision score of 43%.
  ![download (1)](https://github.com/skreddypalvai/7MlWQpaQ38udIkNh---Apziva-Project/assets/137756791/2ee0a0c1-475c-497d-b37d-f32a39f26474)
* The SHAP analysis shows that duration, contact method, and marital status are important features:
  ![download (1)](https://github.com/skreddypalvai/7MlWQpaQ38udIkNh---Apziva-Project/assets/137756791/f24234db-a918-472b-9d8c-b2ff1382c94f)

You can see two different colors. If there are more blue values on the negative side of the SHAP graph, it indicates that lower values of the feature have a stronger negative impact on the model's prediction. In this case, lower 'duration' values have a negative impact on the model.

##### **Adaboost Classifier**
*  The Adaboost classifier reached 93% accuracy and a 78% ROC-AUC score. After fine-tuning hyperparameters and fitting, it achieved an average F1 score of 76%, which outperforms the other two models.
  ![download (1)](https://github.com/skreddypalvai/7MlWQpaQ38udIkNh---Apziva-Project/assets/137756791/5bff766c-5be6-4b7c-8fde-4347fb891af7)

* The Adaboost's SHAP analysis reveals the same three most important features as the Random Forest model.
  ![download (1)](https://github.com/skreddypalvai/7MlWQpaQ38udIkNh---Apziva-Project/assets/137756791/efd9be82-88b8-47c9-bd48-72f3b1c87ed1)

#### **Conclusion**:
In summary, the most crucial feature is 'duration', followed by 'contact' and 'marital_status'. When examining the "duration" feature, you'll observe that it often has a low value alongside a negative SHAP value. This indicates that having less duration tends to result in a less favorable outcome. Therefore, European banking institutions should prioritize features like duration, contact method, and marital status. They should aim to extend the duration of interactions with customers to enhance the likelihood of subscriptions.
