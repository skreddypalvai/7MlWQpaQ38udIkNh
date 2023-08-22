#### **Summary**:
A small startup is mainly focused on providing machine learning solutions in the European banking market. They tackle a variety of challenges, including fraud detection, sentiment classification, and predicting and classifying customer intentions. Currently, their interest lies in developing a robust machine learning system that utilizes information derived from call center data.
Their ultimate goal is to enhance the success rate of customer calls for the products offered by their clients.

To achieve this, We need to design an ever-evolving machine learning product that delivers high success outcomes while ensuring interpretability for their clients, allowing them to make well-informed decisions.

#### **Data Dictionary**:
The data is collected from direct marketing efforts of a European banking institution. The marketing campaign involves making a phone call to a customer, often multiple times to ensure a product subscription, in this case a term deposit. Term deposits are usually short-term deposits with maturities ranging from one month to a few years. The customer must understand when buying a term deposit that they can withdraw their funds only after the term ends. Overall, dataset contains 40000 rows and 14 columns.
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
Main goal is to predict  if the customer will subscribe to a term deposit or not. Most of the features are categorical and only few are numerical, we need to analyze them efficiently by fitting the best models with optimal parameter values. We will be using cross validation techniques for better evaluation.
