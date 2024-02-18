# Customer churn Analysis-Dashboard

 # Report Snapshot (Power BI DESKTOP)
![churn customer view](https://github.com/ErinfolamiMayowa/PowerBI/assets/137004080/a02fcee9-19ee-4c44-94e4-195d4ac121bc)


## Problem Statement

This dashboard helps the bank understand their customers better. It provides the bank with more insight into activities relating to their customers on a month to month and year to year basis. Through different credit score ratings, they get to know the customers category that are exiting from their services & thus they can improve their services by identifying these area. it help them know the number of retained customers, inactive,exit customer, number of customers having credit card and gender distribution of the customers. 

This dashboard help them in identifying areas where they can improve their services.


### Steps followed 

- Step 1 : Load data from multiple source into Power BI Desktop, 
- Step 2 : Open power query editor & in view tab under Data preview section, check "column distribution", "column quality" & "column profile" options.
- Step 3 : Also since by default, profile will be opened only for 1000 rows so you need to select "column profiling based on entire dataset".
- Step 4 : Calculated column was created in which customers were grouped into various credit rating based on credit score.

for creating new column following DAX expression was written;
       
        Credit Score = SWITCH(TRUE(),BankChurn[CreditScore] >= 800 && BankChurn[CreditScore] <= 850, "Excellent",
BankChurn[CreditScore] >= 740 && BankChurn[CreditScore] <= 799, "Very Good",
BankChurn[CreditScore] >= 670 && BankChurn[CreditScore] <= 739, "Good",
BankChurn[CreditScore] >= 580 && BankChurn[CreditScore] <= 669, "Fair",
BankChurn[CreditScore] >= 300 && BankChurn[CreditScore] <= 579, "Poor") .
- Step 5 : Calculated measure was created for total customer, active customers,exit customers, non cardholders,%churn, previous month exit customers.
- Step 6 :  In the visualizations pane in report view cluster bar chart was used to represent the credit ratings. 
- Step 7 : Visual filters (Slicers) were added for four fields named "Year", "GeographyLocation", "Month","ExitCategory" & "GenderCategory".
- Step 8 : A bar chart was also added to the report design area representing the number of customers per year grouped into active and inactive . 
        
 - Step 9 : New measure was created to find  % churn,
 
 Following DAX expression was written to find % churn,
 
         % Churn = 
VAR EC = [Exit Customers]
VAR TC = 'Calculations'[Total Customer]
VAR CHURNERPER = DIVIDE(EC,TC)
RETURN CHURNERPER
- Step 10 : The report was then published to Power BI Service.

# Insights

A single page report was created on Power BI Desktop & it was then published to Power BI Service.

Following inferences can be drawn from the dashboard;

### [1] Total Number of Customers = 10000

   Number of active Customers = 5151

   Number of Inactive Customers = 4849 

   Number of Exit customers  = 2037

   Number of Non Cardholder Customers  = 2945


           thus,  number of inactive customers outweight exit customer but the inactive customer are likely to join the exit customer if there are no effort to make them join the list of active customers.
           
### [2] Females make up 55.92% of  exit customer.


