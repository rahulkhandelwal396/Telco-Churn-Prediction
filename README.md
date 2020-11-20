# Telco Churn Prediction

This project is about predicting whether a customer will change telecommunications provider, something known as "churning".

### File descriptions

<ul>
  <li> train.csv - the training set - Contains 4250 lines with 20 columns. 3652 samples (85.93%) belong to class churn=no and 598 samples (14.07%) belong to class churn=yes </li>
  <li>test.csv - the test set - Contains 750 lines with 20 columns: the index of each sample and the 19 features (missing the target variable "churn"). </li>
</ul>

### Data fields

| Field  | Understanding |
| ------------- | ------------- |
| state  | string. 2-letter code of the US state of customer residence  |
| account_length  | numerical. Number of months the customer has been with the current telco provider  |
| area_code | string="area_code_AAA" where AAA = 3 digit area code.  |
| international_plan  | (yes/no). The customer has international plan.  |
| voice_mail_plan  | (yes/no). The customer has voice mail plan.  |
| number_vmail_messages  | numerical. Number of voice-mail messages.  |
| total_day_minutes  | numerical. Total minutes of day calls.  |
| total_day_calls  | numerical. Total number of day calls.  |
| total_day_charge  | numerical. Total charge of day calls.  |
| total_eve_minutes  | numerical. Total minutes of evening calls.  |
| total_eve_calls  | numerical. Total number of evening calls. |
| total_eve_charge  | numerical. Total charge of evening calls.  |
| total_night_minutes  | numerical. Total minutes of night calls.  |
| total_night_calls  | numerical. Total number of night calls.  |
| total_night_charge  | numerical. Total charge of night calls.  |
| total_intl_minutes  | numerical. Total minutes of international calls.  |
| total_intl_calls  | numerical. Total number of international calls.  |
| total_intl_charge  | numerical. Total charge of international calls  |
| number_customer_service_calls  | numerical. Number of calls to customer service  |
| churn  | Customer churn - target variable. |

### Project Flow

<ol>
 <li>Importing and investigating the data</li>
 <li>Data Pre-processing</li>
 <li>Train-Test Split</li>
 <li>Random Forest Model</li>
 <li>Logistic Regression Model</li>
 <li>K-Nearest Neighbors Model</li>
 <li>Model Comparison</li>
 <li>Results</li>
</ol>

### 1. Importing and investigating the data

After importing both the training and testing data, we check information about the train set by calling the .info() method:

<img src = 'train_info.png' width = "400" height = "300"/>

As we can see, the data does not contain any null values. There are two types of numerical data in the dataframe - int64 and float64. The categorical data is mentioned against object datatype.

### 2. Data Pre-processing

Checking the distribution of the target variable first:

<img src = 'churn_barplot.png' width = "400" height = "300"/>

Almost ~86% cases belong to churn=0 case while ~14% cases belong to churn=1 case.

* Categorical columns:

Used select_dtypes method to take up columns with datatype = object.
<p>['state', 'area_code', 'international_plan', 'voice_mail_plan']</p>

Preprocessing on categorical columns -> One Hot Encoding

<hr>

* Numerical columns:

Used select_dtypes method to take up columns with datatype = int64|float64.
<p>['account_length', 'number_vmail_messages', 'total_day_minutes',
       'total_day_calls', 'total_day_charge', 'total_eve_minutes',
       'total_eve_calls', 'total_eve_charge', 'total_night_minutes',
       'total_night_calls', 'total_night_charge', 'total_intl_minutes',
       'total_intl_calls', 'total_intl_charge',
       'number_customer_service_calls']</p>
       
Preprocessing on numerical columns -> Standard Scaling   

A Pipeline method was created to facilitate data preprocessing. Target column 'churn' was label-encoded.

### 3. Train-Test Split

Data was split into training and testing sets using sklearn.model_selection library. 
Train_size = 66.67%
Test_size  = 33.33%

### 4. Random Forest Model


### 5. Logistic Regression Model


### 6. K-Nearest Neighbors Model



### 7. Model Comparison

Table with accuracy in percentage of all the models:
<img src = 'Model table.png' width = "200" height = "100"/>

### 8. Results

Graphical comparison:
<img src = 'Model Comparison.png' width = "400" height = "300"/>
