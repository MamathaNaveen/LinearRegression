Lending Club
Banks and Finance Companies are often keen to provide various loan schemes such as Housing Loans, Personal Loans, Credit Cards etc. as interest from the loan are one of their primary source of revenue. However, defaulting or non-payment of loans results into potential financial losses for these institutions. Therefore, it is very crucial to assess all risks before approving a loan to an applicant. The main purpose of this project is to identify the key factors behind loan defaults, thereby assisting the company in recognizing risky loan applications for better decision making.

README1

Table of Contents
General Info
Technologies Used
Conclusions
General Information
When a person applies for a loan, there are two types of decisions that could be taken by the company:

Loan accepted: If the company approves the loan, there are 3 possible scenarios described below:

Fully paid: Applicant has fully paid the loan (the principal and the interest rate)

Current: Applicant is in the process of paying the instalments, i.e. the tenure of the loan is not yet completed. These candidates are not labelled as 'defaulted'.

Charged-off: Applicant has not paid the instalments in due time for a long period of time, i.e. he/she has defaulted on the loan

Loan rejected: The company had rejected the loan (because the candidate does not meet their requirements etc.). Since the loan was rejected, there is no transactional history of those applicants with the company and so this data is not available with the company (and thus in this dataset)

The company wants to understand the driving factors (or driver variables) behind loan default, i.e. the variables which are strong indicators of default. The company can utilise this knowledge for its portfolio and risk assessment.

The study identifies how consumer attributes and loan attributes influences the tendency of default.

The dataset considered for this study can be found here - https://github.com/MallikaBera/LendingClubCaseStudy/blob/feb436f1e086c5362ff26a3953b0d8e63828805c/loan.zip

Conclusions
Loans approved should have lower interest Rate. Amounts loaned at higher interest rates(typically more than 13.5%) are mostly charged-off.

For higher rate of interest, the annual income of the applicant should be high (approx. more than 83K) for a safer decision.

Amounts for loan subgrades of A & B should be favored over the remaining to reduce charged-offs rates.

Number of loans defaulted is lesser in count for housing loan customers who owns the house while it is more for the ones with rented or mortgaged properties.

Short term(36 months) loans are defaulted more often than long term loans(60 months).

Investments on Renewable Energy should be increased and Debt Consolidation should be reduced.

Applicants from Canada and NY have more chances to be defaulters.

Credit pull for LCs should continue at the same rate.

Applicants with Low/Moderate Annual Income and more than average to high Debt ratio should be validated carefully before approving the loan application.

Technologies Used
Python - version 3.11.1
Python Numpy - version 1.26.4
Python Pandas - version 2.1.4
Python Matplotlib - version 3.7.3
Python Seaborn - version 0.12.2
Contact
Created by @mallikabera and @MamathaNaveen - feel free to contact us!
