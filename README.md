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
