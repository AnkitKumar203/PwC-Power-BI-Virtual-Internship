# PwC-Power-BI-Virtual-Internship
## PWC Power BI Virtual work experience - Diversity and Inclusion Analysis
![Screenshot (1431)](https://github.com/akgitthub/PwC-Power-BI-Forage-/assets/108720095/5c37e602-de6a-476a-a6f5-6254b1fc77d7)

**Table of Contents:**
* Problem Statement
* Datasource
* Data Preparation
* Data Modeling
* Data Analysis (DAX)
* Data Visualization (Dashboard)
* Insights
### Problem Statement :
The purpose of this task is to:

Define proper KPIs in hiring, promotion, performance and turnover
Create a visualisation for the HR manager that reflects all relevant Key Performance indicators(KPIs) and metrics in the dataset.

**Calculating the following measures could help to define proper KPIs:**

* Number of men
* Number of women
* Number of leavers
* % employees promoted (FY21)
* % of women promoted
* % of hires men
* % of hires women
* % turnover
* Average performance rating: men
* Average Performance rating: women
### Datasource :
Dataset used for this task was presented by Pwc and Diversity and Inclusion dataset:

**Dataset: Diversity and Inclusion**

# Data Preparation:
Completed the Data transformation in Power Query and the dataset loaded into Microsoft Power BI Desktop for modeling.

Diversity and Inclusion dataset is give table named:

Diversity and Inclusion dataset which has 500 rows and 31 Column of observation
Data Cleaning for the dataset was done in the power query editor as follows:

Changed the header row of dataset
Replaced the value is New hire FY20? N coverted No and Y converted Yes
Replaced the value is In base group for turnover FY20 N coverted No and Y converted Yes
Replaced the value is Promotion in FY20? N coverted No and Y converted Yes
Removed Unnecessary columns
Removed Unnecessary rows
Each of the columns in the table were validated to have the correct data type

## Data Analysis (DAX):
**Measures used in all visualization are:**

* #of leavers = CALCULATE(COUNTA('HR Manager'[Employee ID]), 'HR Manager'[Leaver FY] IN { "FY20" })

* #of men =Calculate(distinctcount('HR Manager'[Employee ID]),Filter('HR Manager','HR Manager'[Gender]="Male"))

* #of women = Calculate(distinctcount('HR Manager'[Employee ID]),Filter('HR Manager','HR Manager'[Gender]="Female"))

* % employees promoted (FY21) =Divide(Calculate(distinctcount('HR Manager'[Employee ID]),Filter('HR Manager','HR Manager'[Promotion in FY21?]="Yes")),Calculate(distinctcount('HR Manager'[Employee ID]),Filter('HR Manager','HR Manager'[In base group for Promotion FY21]="Yes")))

* % of hires men = Divide('HR Manager'[# of men],('HR Manager'[# of men]+'HR Manager'[# of women]))

* % of hires women = Divide('HR Manager'[# of women],('HR Manager'[# of women]+'HR Manager'[# of men]))

* % Promotees who were men = Divide(Calculate(distinctcount('HR Manager'[Employee ID]),Filter('HR Manager','HR Manager'[Gender]="Male")),distinctcount('HR Manager'[Employee ID]))

* % Promotees who were women = Divide(Calculate(distinctcount('HR Manager'[Employee ID]),Filter('HR Manager','HR Manager'[Gender]="Female")),distinctcount('HR Manager'[Employee ID]))

* % Turnover = Divide(Calculate(distinctcount('HR Manager'[Employee ID]),Filter('HR Manager','HR Manager'[FY20 leaver?]="Yes")),Divide(Calculate(distinctcount('HR Manager'[Employee ID]),Filter('HR Manager','HR Manager'[In base group for turnover FY20]="Y"))+Calculate(distinctcount('HR Manager'[Employee ID]),Filter('HR Manager',NOT('HR Manager'[Department @01.07.2020]=BLANK()))),2))

* Avg Rating Men = Calculate(Average('HR Manager'[FY20 Performance Rating]),Filter('HR Manager','HR Manager'[Gender]="Male"))

* Avg Rating Women = Calculate(Average('HR Manager'[FY20 Performance Rating]),Filter('HR Manager','HR Manager'[Gender]="Female"))

## Data Visualization:
**Data visualization for the data analysis (DAX) was done in Microsoft Power BI Desktop:**

**_Dashboard:_** https://www.novypro.com/project/diversity--inclusion-dashboard-6

### Shows visualizations from Diversity and Inclusion:

**Diversity and inclusion HR Dashboard 1**

![Screenshot (1428)](https://github.com/akgitthub/PwC-Power-BI-Forage-/assets/108720095/e69c0fe1-bf3e-4640-a0a3-2e4037f55b08)

**Diversity and inclusion HR Dashboard 2**
![Screenshot (1429)](https://github.com/akgitthub/PwC-Power-BI-Forage-/assets/108720095/21370ffc-64f3-4b04-a638-ed02bf628ea9)

**Diversity and inclusion HR Dashboard 3**
![Screenshot (1430)](https://github.com/akgitthub/PwC-Power-BI-Forage-/assets/108720095/4977f11e-906c-4587-b967-f981bd423b85)


## Insights:
**As shown the data Visualization, It can be deduced that:**

* 41 % Female hires of the year and 59 % Male hires of the years.
* 53.8% of promoted were Female in the Junior Officer category, the highest for the year.
* 47% of promoted were Male in the Junior Officer category, the lowest for the year.
* Director is the highest Average time of job level promoted in this year.
* Finance department 22% highest turnover of the year.
* Average Rating Female 2.42%
* Average Rating Male 2.41%
* Employees promoted year of 2021 is 54.34% Male and 45.66% Female.
* The most common age group is 20-29 having 223 employees fall in this category.

## PWC Power BI Virtual work experience- Call Centre Trends

**Table of Contents :**

* Problem Statement
* Datasource
* Data Preparation
* Data Modelling
* Data Analysis (DAX)
* Data Visualization Dashboard
* Insights
**Problem Statement :**
In this project Create a dashboard in Power BI for the call center manager that reflects all relevant Key Performance Indicators (KPIs) and metrics in the dataset.

_Possible KPIs include (but not limited to):_

Overall customer satisfaction
Overall calls answered/abandoned
Calls by time
Average speed of answer
Agent’s performance quadrant -> average handle time (talk duration) vs calls answered
### Datasource :
Dataset used for this task was presented by Pwc and call centre trends dataset:

**Dataset: Call Centre Trends**

## Data Preparation:
Completed the Data transformation in Power Query and the dataset loaded into Microsoft Power BI Desktop for modeling.

Call Centre Trends dataset is give table named:

Call Center trends dataset which has 10 columns and 5000 rows of observation
Data Cleaning for the dataset was done in the power query editor as follows:

Removed Unnecessary columns
Removed Unnecessary rows
Each of the columns in the table were validated to have the correct data type
Data Modeling:
And then dataset was cleaned and transformed, it was ready to the data modeled.

**The measure table and call centre trends tables as show below:**
-Screenshot (37)

* Data Analysis (DAX):
* **Measures used in all visualization are:**

* Average of seed of answerd = AVERAGE('call centre trends'[Speed of answer in seconds])

* Average of statisfaction = AVERAGE('call centre trends'[Satisfaction rating])

* Count satisfation rating = COUNT('call centre trends'[Satisfaction rating])

* Overall Customer Satisfation = DIVIDE([Possitive satisfation rating],[Count satisfation rating],0)

* Possitive satisfation rating = CALCULATE(COUNT('call centre trends'[Satisfaction rating]),FILTER('call centre trends','call centre trends'[Satisfaction rating] IN {4,5}))

* resolved calls = COUNTX(FILTER('call centre trends','call centre trends'[Resolved] = "Yes"), 'call centre trends'[Resolved])

* Unresolved calls = COUNTX(FILTER('call centre trends','call centre trends'[Resolved] = "No"), 'call centre trends'[Resolved])

* total calls = CALCULATE('Table'[total calls answered] + 'Table'[total calls unanswred])

* total calls answered = COUNTX(FILTER('call centre trends','call centre trends'[Answered (Y/N)] = "Yes"),'call centre trends'[Answered (Y/N)])

* total calls unanswred =COUNTX(FILTER('call centre trends','call centre trends'[Answered (Y/N)] = "No"), 'call centre trends'[Answered (Y/N)])

**Data Visualization (Dashboard)**
Data visualization for the data analysis (DAX) was done in Microsoft Power BI Desktop.

Dashboard: [View Dashboard](https://shorturl.at/syAU7)

**Shows visualizations from Call Center Trends :**

### Call Centre Trends (Overview)
**PWC Task 1 - Call Centre Dashboard-1**

![Screenshot (1425)](https://github.com/akgitthub/PwC-Power-BI-Forage-/assets/108720095/68566dd8-1f45-4544-8f17-65e074e17207)

### Insights :
**As shown by Data Visualization, It can be deduced that:**

* Most of the satisfaction ratings from each call are 3 and 4.
* The average satisfaction rating has decreased over the span of three months. January brought the highest satisfaction rating and march the lowest.
* The percentage of issue resolved in January was the highest, with a dip in February. It increased again in march.
* The majority of calls come in the morning.
* The average speed of answer by Joe is the highest.
* The call resolution rate of Jim is the highest, even though the average speed of his answers is lower compared to those of Joe, Martha and Dan. The call answered by - him are also higher than the average number of calls answered.
* Becky's speed of answer is the lowest among all, and her rate of calls resolved is higher. She is in the 5th position in the call resolution rate.
* Martha has the highest speed of answered in the sec

# PWC Power BI Virtual work experience - Customer Churn Retention

**Table of Contents:**

* Problem Statement
* Datasource
* Data Preparation
* Data Modeling
* Data Analysis (DAX)
* Data Visualization (Dashboard)
* Insights
* Recommendation

**Problem Statement :**

The purpose of this task is to:

Define proper KPI's
Create a dashboard for the retention manager reflecting the KPI's
Write a short email to him (the engagement partner) explaining your findings, and include suggestions as to what needs to be changed
Customers who left within the last month
Services each customer has signed up for: phone, multiple lines, internet, online security, online backup, device protection, tech support, and streaming TV and movies
Customer account information: how long as a customer, contract, payment method, paperless billing, monthly charges, total charges and number of tickets opened in the categories administrative and technical
Demographic info about customers – gender, age range, and if they have partners and dependents

**Datasource :**

Dataset used for this task was presented by Pwc and customer churn Retention dataset:

**Dataset: Customer Churn Retention**

## Data Preparation:

Completed the Data transformation in Power Query and the dataset loaded into Microsoft Power BI Desktop for modeling.

Customer Churn dataset is give table named:

Customer churn dataset which has 23 columns and 7043 rows of observation
Data Cleaning for the dataset was done in the power query editor as follows:

Replaced the value is SeniorCitizen N coverted No and Y converted Yes
In the new table, one additional conditional columns were added using M-formula:

* loyalty = SWITCH(TRUE(),'01 Churn-Dataset'[tenure]<=12,"< 1 year",'01 Churn-Dataset'[tenure]<=24,"< 2 years",'01 Churn-Dataset'[tenure]<=36,"< 3 years",'01 Churn-Dataset'[tenure]<=48,"< 4 years", '01 Churn-Dataset'[tenure]<=60,"< 5 years",'01 Churn-Dataset'[tenure]<=72,"< 6 years")

Removed Unnecessary columns

Removed Unnecessary rows

Each of the columns in the table were validated to have the correct data type

**Data Modeling:**

And then dataset was cleaned and transformed, it was ready to the data modeled.

**The customer churn tables as show below:**

![Screenshot (1417)](https://github.com/akgitthub/PwC-Power-BI-Forage-/assets/108720095/021b6284-6bd1-4eef-a00a-b4ddb027a14f)


## Data Analysis (DAX):

**### Measures used in all visualization are:**

* Average MonthlyCharges = AVERAGE('01 Churn-Dataset'[MonthlyCharges])

* Average TotalCharges = AVERAGE('01 Churn-Dataset'[TotalCharges])

* churn count = CALCULATE(COUNT('01 Churn-Dataset'[Churn]), ALLSELECTED('01 Churn-Dataset'[Churn]),'01 Churn-Dataset'[Churn] = "Yes")

* churn rate % = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[Churn]), '01 Churn-Dataset'[Churn] = "yes" ), COUNT('01 Churn-Dataset'[Churn]), 0)

* Dependent in % = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[Dependents]), '01 Churn-Dataset'[Dependents]="Yes",'01 Churn-Dataset'[Churn]="Yes"), CALCULATE(COUNT('01 Churn-Dataset'[Dependents]),'01 Churn-Dataset'[Churn]="Yes"), 0)

* Device protection in % = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[DeviceProtection]), '01 Churn-Dataset'[DeviceProtection] ="Yes", '01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[DeviceProtection]),'01 Churn-Dataset'[Churn]="Yes"),0)

* Online backup in % = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[OnlineBackup]), '01 Churn-Dataset'[OnlineBackup] ="Yes", '01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[OnlineBackup]),'01 Churn-Dataset'[Churn]="Yes"),0)

* Online security in % =DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[OnlineSecurity]), '01 Churn-Dataset'[OnlineSecurity] ="Yes", '01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[OnlineSecurity]),'01 Churn-Dataset'[Churn]="Yes"),0)

* Partner in % = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[Partner]),'01 Churn-Dataset'[Partner]="Yes",'01 Churn-Dataset'[Churn]="Yes"), CALCULATE(COUNT('01 Churn-Dataset'[Partner]), '01 Churn-Dataset'[Churn]="Yes"), 0)

* Phone service in % =DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[PhoneService]), '01 Churn-Dataset'[PhoneService] ="Yes", '01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[PhoneService]),'01 Churn-Dataset'[Churn]="Yes"),0)

* SenioCitizen in % = DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[SeniorCitizen]),'01 Churn-Dataset'[SeniorCitizen]=1,'01 Churn-Dataset'[Churn]="Yes"), CALCULATE(COUNT('01 Churn-Dataset'[SeniorCitizen]),'01 Churn-Dataset'[Churn]="Yes"), 0)

* Streaming Movies in % =DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[StreamingMovies]), '01 Churn-Dataset'[StreamingMovies] ="Yes", '01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[StreamingMovies]),'01 Churn-Dataset'[Churn]="Yes"),0)

* Streaming TV in % =DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[StreamingTV]), '01 Churn-Dataset'[StreamingTV] ="Yes", '01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[StreamingTV]),'01 Churn-Dataset'[Churn]="Yes"),0)

* Tech Support in % =DIVIDE(CALCULATE(COUNT('01 Churn-Dataset'[TechSupport]), '01 Churn-Dataset'[TechSupport] ="Yes", '01 Churn-Dataset'[Churn]="Yes"),CALCULATE(COUNT('01 Churn-Dataset'[TechSupport]),'01 Churn-Dataset'[Churn]="Yes"),0)

## Data Visualization (Dashboard):
**Data visualization for the data analysis (DAX) was done in Microsoft Power BI Desktop**:

**Dashboard:** https://www.novypro.com/project/pwc-phonenow-churn-dashboard-analysis


**Shows visualizations from Customer Retention analysis:**

### Customer Churn

![Screenshot (1422)](https://github.com/akgitthub/PwC-Power-BI-Forage-/assets/108720095/57726071-8f66-434e-8a3b-39daab5a6dbc)

### Customer Risk

![Screenshot (1418)](https://github.com/akgitthub/PwC-Power-BI-Forage-/assets/108720095/e268bdf7-bfd4-4f09-b35b-c7f64d7e688d)

### Services

![Screenshot (1420)](https://github.com/akgitthub/PwC-Power-BI-Forage-/assets/108720095/38468c14-ff5b-40ea-ba52-f915fcea49f7)

### Insights:
**As shown the data Visualization, It can be deduced that:**

* Customers on the Two-Year contract, have been with the company for long, while most of the customers on Month-to-Month contract joined the company.
* The company is at risk of losing recently joined customers. based on the results from analysis.. if they decided to month-to-month contract.
* 7043 customers are at the risk of churn. and The churn rate is 27% and yearly charges is $16.06M charges. and Monthly Charges is $456.12K monthly charges.
* 2955 tech tickets were opened and 3632 admin tickets were opened.
* Most of the churned customers did not sign up for Online Security and tech support and also did not sign up for Phone Services.
* It a lot of customers had an issue with Fiber Optic . Up to 42% of the customers churned were using Fiber Optic as their Internet Services.

**Recommendation:**

The Company could try convincing customers to subscribe to One-Year and Two-Year contract. The contract are not favorable to customers as they tend to pay more monthly.
Giving the discount to customers based on the some specific tasks is also good wat retaining them, specially those month-to-month contract.
From analysis majority customers who churned did not sigh up for Online Security and Tech Support. These are the important services that customers should customers signup for. The company should educate customers on the benefits of signing up for these services.
Increase sale of 1 and 2 year contract by 5% each and Yearly increase of automatic payments by 5%.

