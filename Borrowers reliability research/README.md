## Project: Borrowers reliability research
* **Description**: The client is a bank's credit department. It is necessary to understand whether the client’s marital status and the number of children affect the fact of repaying the loan on time. The results of the study will be taken into account when constructing a credit scoring model - a special system that assesses the ability of a potential borrower to repay the loan to the bank.
* **Goal**: Determine the factors that affect the non-repayment of the credit on time.
* **Tools**: `Python`, `Pandas`, `Seaborn`, `Matplotlib`, `Data Preprocessing`
* **Activity Area** : Banking, Crediting
* **Technical Area**: `Data Analysis`
*  **Data**:
  - children — number of children in the family
  - days_employed — total length of service in days
  - dob_years — client age in years
  - education — client’s education level
  - education_id — education level identifier
  - family_status - marital status
  - family_status_id — marital status identifier
  - gender - client gender
  - income_type — employment type
  - debt - whether there was a debt to repay loans
  - total_income - monthly income
  - purpose — purpose of obtaining a loan

### Results:

- People with no children are the best at repaying loans. The share of debtors here is 7.54%. The situation is worse with debtors who have one or two children, the share of non-repayment is 9.23% and 9.45% here, respectively.

- People who are married are the best at repaying loans. The share of debtors here is 7.56%. The situation is worse with debtors who are single and those in a civil marriage. The share of non-return is 9.76% and 9.31% here, respectively.

- People with income category 'B' are the best at repaying loans. The share of debtors here is 7.06%. The situation is worse for debtors who have income category 'C'. The non-return rate is 8.50% here.

- People whose loan purpose is "real estate transactions" are the best at repaying the loan, with a debt percentage of 7.26%. The worst debt repayers are those who take out a loan to buy cars or pay for education, with debt percentages of 9.35% and 9.25%, respectively (a difference of 1.07%).

This is the classification of the factors that most affect the non-payment of debts, from the greatest to the least:

- Family status - 22.54%
- Loan goals - 22.35%
- Number of children in the family - 20.21%
- Income level - 16.94%
- The difference between family status and loan target is 0.84% The difference between family status and number of children is 10.34% The difference between family status and income level is 24.84%

That is, special attention should be paid to the family status of the borrowers, as well as their goals for the loan and the number of children.
