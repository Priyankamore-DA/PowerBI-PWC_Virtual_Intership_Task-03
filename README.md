# PWC-Switzerland-PowerBI-virtual-case

## Task 3-Customer Retention-Customer demographics and insights.



###  *Table of Contents:

#### •		Problem Statement

#### •		Flow of work-:
```             
Step 1- Upload Data
             
Step 2-Cleaning data
            
Step 3-Transform data
             
Step 4-Load data 
```
#### •	Data Preparation
```
Data Modelling

Writing DAX 
```
#### •		Data Visualization

#### •		Data Analysis

#### •		Insights

#### •		Shareable link






#### •Problem Statement
The telecom Retention Manager has scheduled a meeting with the engagement partner at PwC to cover these points:

 •		Customers in the telecom industry are hard-earned: we don’t want to lose them.
 
 •		The retention department is here to get customers back in case of termination.
 
 •		Currently, we get in touch after they have terminated the contract, but this is reactionary: it would be better to know in advance who is at risk.
 
 •		We  have done customer analysis with Excel: it has always ended in a dead-end.
 
 •		We would like to know more about our customers: visualised clearly so that it’s self-explanatory for our management.

Your colleague, the engagement partner, asks you to do the following tasks:

 1)	Define proper KPIs

 2)	Create a dashboard for the retention manager reflecting the KPIs

 3)	Write a short email to him (the engagement partner) explaining your findings, and include suggestions as to what needs to be changed

Here are some inputs:

 •		Customers who left within the last month
 
 •		Services each customer has signed up for: phone, multiple lines, internet, online security, online backup, device protection, tech support, and streaming TV and movies
 
 •		Customer account information: how long as a customer, contract, payment method, paperless billing, monthly charges, total charges and number of tickets opened in the categories administrative and technical
 
 •		Demographic info about customers – gender, age range, and if they have partners and dependents
 
 
#### •	Flow of work

##### Step 1- Upload Data

The Dataset used for this analysis was presented by PWC_Switzerland and available at their official website page - [Dataset_link]

##### Step 2-Cleaning data

Data transformation was done in Power Query and the dataset was loaded into Microsoft Power BI Desktop for modelling.The Customer Retention dataset is given by a table named:

•	Customer retention which has `23 columns and 7043 rows` of observation

The tabulation below shows the Customer retention table with its column names and their description:

| Column Name	    | Description     | 
| ------------- | ------------- | 
| `customerID`        |Represents the unique number of the customer in the dataset|
| `gender`         | Describes the gender of the customer |
| `SeniorCitizen` |    	                Describes if the customer is a senior citizen|
| `Partner` |	                       Describes if the customer has a partner|
|`Dependents` |                      	Describes if the customer has a dependent|
| `tenure`                     |Describes how long as a customer|
|  `PhoneService`	                    |Describes if the customer has registered a phone service|
| `MultipleLines`	|Describes if the customer has registered multiple lines|
| `InternetService`              |	Describes if the customer has registered for internet service|
| `OnlineSecurity`	        |Describes if the customer has registered for online security|
| `OnlineBackup`	        |Describes if the customer has registered for online backup|
| `DeviceProtection`	        |Describes if the customer has registered for device protection|
| `TechSupport`	        |Describes if the customer has registered for tech support|
| `StreamingTV`	        |Describes if the customer has registered to stream tv|
| `StreamingMovies`	        |Describes if the customer has registered to stream movies|
| `Contract`	        |Describes if the length of the contract of the customer|
| `PaperlessBilling`	        |Describes if the customer has registered for paperless billing|
| `PaymentMethod`	        |Describes the payment method of the customer|
| `MonthlyCharges`	        |Represents the monthly charge incurred by the customer|
| `TotalCharges`	        |	Represents the total charge incurred by the customer|
| `numAdminTickets`	        |Represents the number of admin tickets opened by the customer|
| `numTechTickets`	        |Represents the number of tech tickets opened by the customer|
| `Churn`	        |Describes if the customer is at risk of churn|



##### Step 3-Transform data
Data Cleaning and transformation for the dataset were done in power query as follows:
•	Each of the columns in the table was validated to have the correct data type
•	Unnecessary rows were removed

#### Data preparation: -

##### Data Modelling
After the dataset was cleaned and transformed, it was ready to be modelled.
•	The official dataset is marked as the `01 CHURN-Dataset` table in the dataset.
       
•	Along with this, a separate table- All Measuress is created to store all the measures which we have used in this model.

##### Data Visualization
Data visualization for the datasets was done in Microsoft Power BI Desktop:

•	`Demographic` Info : Shows the male-female distribution,churn by senior citizen,dependents impact,partner impact effect of internet service provider recommendations and a short insight on the report

•	`Account Info` : shows contrct type payment method tenuraity impact on customer count total charges, average monthly charges etc

•	`Services` : shows customer count by streamingTV,customer count by streamingmovies,churn by phoneservice,online security device protection,Tech support etc

•	`Email / Insights and suggestion` :Insights ans suggestions to the engagement partner explaining  findings, and include suggestions as to what needs to be changed

#### Data Analysis
Measures used in visualization are:

•	`Answered_call` = CALCULATE(COUNT('Fact Table'[Call Id]),FILTER('Fact Table','Fact Table'[Answered (Y/N)]="Y"))

•	`Resolved count` = CALCULATE(COUNT('Fact Table'[Call Id]),'Fact Table'[Resolved]="Y")

•	`Avg_rating` = AVERAGE('Fact Table'[Satisfaction rating])

•	`Average speed of answer` = AVERAGE('Fact Table'[Speed of answer in seconds])

•	`Target Value Satisfaction` = 4.5

•	`%Call Answered` = DIVIDE('All Measuress'[Answered_call],[Total_calls],0)

•	`%call resolved` = DIVIDE([Resolved count],[Total_calls],0)

•	`%Call Unanswered` = DIVIDE([Not_answered],[Total_calls],0)

•	`%call unresolved` = DIVIDE('All Measuress'[Unreolved count],[Total_calls],0)

•	`Agent_slicer` = DISTINCTCOUNT('Fact Table'[Agent])

•	`Average speed of answer(IN MIN)` = DIVIDE('All Measuress'[Average speed of answer],60,0)

•	`Avg duration of talk` = AVERAGE('Fact Table'[AvgTalkDuration])

•	`Avg talk of duration (IN MIN)` = DIVIDE('All Measuress'[Avg duration of talk],60,0)

•	`No of agent` = CALCULATE(DISTINCTCOUNT('Fact Table'[Agent]))

•	`Not_answered` = CALCULATE(COUNT('Fact Table'[Call Id]),FILTER('Fact Table','Fact Table'[Answered (Y/N)]="N"))

•	`Total_calls` = COUNTROWS('Fact Table')

•	`Unreolved count` = CALCULATE(COUNT('Fact Table'[Resolved]),'Fact Table'[Resolved]="N")


#### Insights

As shown by Data Visualization, It can be deduced that:

•	Out of all the 7043 customers, 26.54 i.e overall 27 % of the customers churned last month. 

• Customers having short tenure are more frequently switching than customers having longer tenure.

• If no  Tech Support, Device Protection, and Online Security are provided then the chances of customers churning are high.

•  payment method like Electronic check also makes a significant impact on the churning decision.

• There is no relation between gender with churning.  

• senior citizens are less likely to churn rate.

• Customers with any dependents or partners are churning less likely, whereas the non-dependents and non-partners customers are more likely to shift.

• Tenure and contract play an important role in determining whether the customer will churn. Customers with monthly contracts i.e. lower tenure will switch frequently.

• Customers with Fiber Optic internet service will churn more compared to DSL internet service holders.


#### Suggestions
•	Increasing the basic contract plan from 1 month to 3 months or  6 months can be a good starting point. This will help customers to be with us for a longer tenure.

•	Starting special offers or schemes for customers who are single and have no family responsibility. They can become a permanent customer of the company. 'Catch them Young' is key to success here.

•	provide some offers to the senior citizens as they are stable customers like overall offer some discounts on long tenure plans.

•	Offering basic services like device protection, tech support, and online security should be the primary goal. This will help the customer stay longer with the brand.

#### Dashboard image
Figure 1 shows visualizations from `Demographic` Info

![image](https://user-images.githubusercontent.com/127341700/227794003-eabb02dd-3e8e-40c8-9611-79bedba25ce7.png)


Figure 2 shows visualizations from `Account Info`
![image]


Figure 3 shows visualizations from `Services`
![image]



Figure 4 shows visualizations from `Email / Insights and suggestion`
![image]





