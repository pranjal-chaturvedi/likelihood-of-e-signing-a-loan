# Predicting the likelihood of e-signing a loan based on financial history
### Introduction
Lending companies work by analysingthe finanacial history of their loan applicants and choosing whether or not the applicant is too risky to be given a loan. If the applicant is not, the company then determines the terms of the loan. To acquire these applicants, companies can organically receive them through their websites/apps, often with the help of advertisement campaigns. Other times, lending companies partner with peer-to-peer (P2P) lending marketplaces, in order to acquire leads of possible applicants. Some example of marketplaces include Upstart, Lending Tree and Lending Club. In this project, we are going to assess the 'quality' of the leads our company receives from these marketplaces.

* __Market:__ The target audience is the set of loan applicants who reached out through an intermediary marketplace.

* __Product:__ A loan.

* __Goal:__ Develop a model to predict for 'quality' applicants. In this case study, 'quality' applicants are those who reach a key part of the loan application process.

### Business Problem
In this case study we will be working for a fintech company that specalises in loans. It offers low APR loans to applicants based on their financial habits, as almost all lending companies do. This company has partnered with a P2P lending marketplace that provides real-time leands (loan applicants). The numbers of conversions from these leads are satisfactory.

A model is to be created that predicts whether or not these leads will complete the electronic signature phase of the loan application (a.k.a. e_signed). The company seeks to leverage this model to identify less 'quality' applicants (e.g. those who are not responding to the onboarding process), and experiment with giving them different onboarding screens.

The reason for selecting the e_signing process as the response variable is due to the structure of the loan application.

The official application begins with the lead arriving into our website after we opted to acquire it. Here, the applicant begins the onboarding process to apply for a loan. The user begins to provide more financial information by going over every screen of the onboarding process. This first phase ends with the applicant providing his/her signature indicating all of the given information is correct.

Any of the following screens, in which the applicant is approved/denies and given the terms of the loan, is dependent on the company, not the applicant. Therefore the effectiveness of the onboarding is measured up to the moment the applicant stops having control of the application process.

### About the dataset
Because the applicants arrived through marketplace, we have access to their financial data before the onboarding process begins. This data includes personal information like age, and time employed, as well as other financial metrics. Our company utilises these financial data points to create risk scores based on many different risk factors.

In this case study, we are given the set of scores from algorithms built by the finance and engineering teams. Furthermore, the marketplace itself provides us with their own lead quality scores. We will leverage both sets of scores, as well as small list of personal/financial features to predict if the user is likely for respond to our current onboarding process.

The features of the dataset are as follows:
* entry_id: A seven digits, unique ID for an applicant.
* age: Age of the applicant.
* pay_schedule: How often the applicant gets paid (weekly, bi-weekly, semi-monthly, monthly)
* home_owner: Indicates whether the applicant owns a house. 1 if yes, 0 otherwise.
* income: Monthly income of the applicant.
* years_employed: No. of years the applicant has worked.
* current_address_year: No. of years the applicant has been staying in their current address.
* personal_account_m: No. of months the applicant has had their personal account. Used in combination with 'personal_account_y' column.
* personal_account_y: No. of years the applicant has had their personal account. Used in combination with 'personal_account_m' column.
* has_debt: Indicates whether the applicant has any debt.
* amount_requested: Amount of loan the applicant has applied for.
* risk_score: First of the set of 5 risk scores given by the Finance team. Indicates how likely the user is going to pay the loan etc.
* risk_score2 to risk_score_5: Different risk scores based on different factors.
* ext_quality_score and ext_quality_score2: Scores the 'quality' of the applicant based on various factors.
* inquiries_last_month: No. of enquiries the user has had in the last month (no. of time the user has had a 'hard pull' check). 

The label of interest is:
* e_signed: Indicates whether an applicant has completed the e-signing process. 1 if yes, 0 otherwise.
 
Dataset courtesy: [SuperDataScience](https://sds-platform-private.s3-us-east-2.amazonaws.com/uploads/P39-Financial-Data.csv)