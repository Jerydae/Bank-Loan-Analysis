# BankLoanAnalysis


## Table Of Contents

[Project Overview](#project-overview)

[Data Sources](#data-sources)

[Data Cleaning](#data-cleaning)

[Exploratory Data Analysis (EDA)]( exploratory-data-analysis-eda)

[Data Analysis](#data-analysis)

[Findings](#findings)

[Recommendations](#recommendations)

[References](#references)

[Glossary](#glossary)

---

### Project Overview

This is a bank loan analysis/Report over one year period using two dashboards in Excel with the aim of helping the bank monitor and assess their lending activities and performance. The report provides insights into key loan-related metrics and their changes over time and will help make data-driven decisions, track their loans portfolio's health, and identify trends that can inform our lending strategies.

<img width="536" alt="summary" src="https://github.com/Habiba-Hussein/BankLoanAnalysis/assets/147278092/0046a3b8-9899-4fe2-aeb4-15f705f988e2">


<img width="539" alt="Report" src="https://github.com/Habiba-Hussein/BankLoanAnalysis/assets/147278092/4a1304ca-2aea-434e-913e-9cc679fd1e8e">



### Data Sources

The primary source of data used for the report is the “finanacial_loan.csv” file provided by the bank with all details regarding the loan.

### Tools Used

Utilized Excel for cleaning, formatting and Reporting

###  Data cleaning

The accuracy and validity of the data was achieved by:
1.	Loading and inspection of the data
2.	Converted date to appropriate format and generated and a` month` column from it
3.	Handling the missing values
4.	Creation of new columns i.e calculated columns

### Exploratory Data Analysis (EDA)
Some of the questions answered to help achieve the stakeholder needs were:
1. What is the total number loan Applications, Funded amount and amount received back?
2. What is the average Interest Rate across all loans, MTD, and monitoring the Month-over-Month (MoM) variations?
3. What is Average Debt-to-Income Ratio (DTI)? ( to help us gauge borrowers  financial health)
4. Good Loan Applications, funded amount and amount received back
5. Bad Loan Applications, funded amount and amount received back

### Data Analysis

To help answer some of the EDA questions,I utilized the pivot tables:

To generate the good loan vs bad loan column

```=IF(OR([@[loan_status]]="Fully Paid",[@[loan_status]]="Current"),"Good Loan",IF([@[loan_status]]="Charged Off","Bad Loan",""))```

To extract month column from the `date` column

``` =TEXT([@[issue_date]],"MMM")```

For MoM measures

``` (MTD-PMTD)/PMTD	``` i.e Month -to-date ,Previous month-to-date

Getting the total number of good loan applications

``` =GETPIVOTDATA("Count of id",$B$28,"GoodLoanVs BadLoan","Good Loan")```

Total number of applications

```=GETPIVOTDATA("Count of id",$B$3)```

Creation of slicers,for the `grade` and `purpose` to help stakeholders filter by need


### Findings

Based on the analysis:

- The loan applications have constantly increased throughout the year

- The lending status of the bank is good with the goodloan taking 86.18% of the total 

- `Grade F` borrowers have the highest bad loan percentage

- The loans with the purpose of `Major Purchase` and `Wedding` have the best repayment plan

### Recommendations
- The bank should work on strict regulations for `grade F` borrowers and other grades with high bad loan percentage

- The bank should market better to keep increasing the loan applications

### References

Data Tutorials

### Glossary

- BadLoan: Charged off loans
- Goodloan: Loan whose status is Fully paid or Currently paying
- MoM:Month-over-month shows the change in the value of a specific metric as a percentage of the previous month's value.
- Debt-to-Income ratio:is the ratio of their monthly debt payments to their monthly income i.e lower DTI indicates better repayment capacity
- Month-to-date (MTD): A period that starts at the beginning of the current month and extends up to the present date



















