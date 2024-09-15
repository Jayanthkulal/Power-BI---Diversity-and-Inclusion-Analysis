# Power BI-Diversity and Inclusion Analysis
## Problem Statement :
The purpose of this task is to:

- Define proper KPIs in hiring, promotion, performance and turnover
- Create a visualisation for the HR manager that reflects all relevant Key Performance indicators(KPIs) and metrics in the dataset.
Calculating the following measures could help to define proper KPIs:

- Number of men
- Number of women
- Number of leavers
- % employees promoted (FY21)
- % of women promoted
- % of hires men
- % of hires women
- % turnover
- Average performance rating: men
- Average Performance rating: women

## Datasource :
Dataset used for this task was presented by Pwc and Diversity and Inclusion dataset:

Dataset: Diversity and Inclusion

## Data Preparation:
Completed the Data transformation in Power Query and the dataset loaded into Microsoft Power BI Desktop for modeling.

Diversity and Inclusion dataset is give table named:
- Diversity and Inclusion dataset which has 500 rows and 31 Column of observation

Data Cleaning for the dataset was done in the power query editor as follows:
- Removed Unnecessary columns
- Removed Unnecessary rows
- Each of the columns in the table were validated to have the correct data type

## Data Modeling:
And then dataset was cleaned and transformed, it was ready to the data modeled.

The diversity and inclusion tables as show below:

![Screenshot 2024-09-15 184122](https://github.com/user-attachments/assets/2e9b7174-3e4d-429b-9d29-62547525b15e)

## Data Analysis (DAX):
Measures used in all visualization are:

- % hire of men = DIVIDE(CALCULATE(COUNT('HR Manager'[Gender]), 'HR Manager'[Gender]="male"),COUNT('HR Manager'[Gender]),0)
- % hire of women = DIVIDE(CALCULATE(COUNT('HR Manager'[Gender]), 'HR Manager'[Gender]="female"),COUNT('HR Manager'[Gender]),0)
- % promoted who are women = DIVIDE(CALCULATE(COUNT('HR Manager'[Job Level after FY21 promotions]),'HR Manager'[Gender]="female"), COUNT('HR Manager'[Job Level after FY21 promotions]),0)
- % turnover = Divide(Calculate(distinctcount('HR Manager'[Employee ID]),Filter('HR Manager','HR Manager'[FY20 leaver?]="Yes")),Divide(Calculate(distinctcount('HR Manager'[Employee ID]),Filter('HR Manager','HR Manager'[In base group for turnover FY20]="Y"))+Calculate(distinctcount('HR Manager'[Employee ID]),Filter('HR Manager',NOT('HR Manager'[Department @01.07.2020]=BLANK()))),2))
- Avg Rating Men = Calculate(Average('HR Manager'[rating fy20]),Filter('HR Manager','HR Manager'[Gender]="Male"))
- Avg Rating women = Calculate(Average('HR Manager'[rating fy20]),Filter('HR Manager','HR Manager'[Gender]="female"))

## Data Visualization:
Data visualization for the data analysis (DAX) was done in Microsoft Power BI Desktop:

Dashboard: View Dashboard

Shows visualizations from Diversity and Inclusion:
###                                                                 Diversity and Inclusion(1/2)                                              
![Screenshot 2024-09-15 191651](https://github.com/user-attachments/assets/f72d0e1f-e7ae-4e7f-9a5d-3577ad83e84d)

###                                                                 Diversity and Inclusion(2/2)   
![Screenshot 2024-09-15 191701](https://github.com/user-attachments/assets/bef77c1b-a9a8-4cce-ab7c-2169d5c3d3ba)

## Insights:
As shown the data Visualization, It can be deduced that:
- 59% of hires were men, while 41% were women, indicating a gender gap in recruitment favoring men.
  
- Promotions seem to be more favorable for men in higher positions, while women are better represented in Junior Officer promotions (52%).

-There's a noticeable gender gap in promotions at the executive level, with women making up only 13% of executives promoted.

- Female leavers tend to have higher performance ratings than non-leavers, especially at the Junior Officer level (2.6 vs. 1.9).

- For men, performance ratings of leavers vs. non-leavers remain relatively close, but non-leavers generally perform better in higher positions.

- For men, performance ratings of leavers vs. non-leavers remain relatively close, but non-leavers generally perform better in higher positions.

- There is a stark male dominance in executive roles, with 87.5% being male in FY20 and 84.2% in FY21.

- This indicates a slight improvement in gender diversity at the executive level but still showcases a significant gap.

- The majority of the workforce is concentrated in the 20–29 age group, followed by the 30–39 age group.

- There is a strong representation of younger employees at the Junior Officer level, which could impact the overall turnover rate.

- There is a clear disparity in both hiring and promotion rates between men and women, especially in senior positions, suggesting potential barriers to female progression within the organization.





