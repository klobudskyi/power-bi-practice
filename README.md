# power-bi-practice

## Objective:
The primary objective of this project was to build a strong foundation in Power BI for data analytics, demonstrating my ability to visualize, analyze, and derive insights from datasets.

## Description:

[PwC Switzerland Power BI Job Simulation](https://www.theforage.com/simulations/pwc-ch/power-bi-cqxg) on [Forage](https://www.theforage.com/about):

 - Completed a job simulation where I strengthened my PowerBI skills to better understand clients and their data visualisation needs.
 - Demonstrated expertise in data visualization through the creation of Power BI dashboards that effectively conveyed KPIs, showcasing the ability to respond to client requests with well-designed solutions.
 - Strong communication skills reflected in the concise and informative email communication with engagement partners, delivering valuable insights and actionable suggestions based on data analysis.
 - Leveraged analytical problem-solving skills to examine HR data, particularly focusing on gender-related KPIs, and identified root causes for gender balance issues at the executive management level, highlighting a commitment to data-driven decision-making.

## Stages:

### Task №1:

Create a dashboard in Power BI for Claire that reflects all relevant Key Performance Indicators (KPIs) and metrics in the dataset. Get creative! 

Possible KPIs include (to get you started, but not limited to):

- Overall customer satisfaction
- Overall calls answered/abandoned
- Calls by time
- Average speed of answer
- Agent’s performance quadrant → average handle time (talk duration) vs calls answered
  
<img width="715" alt="task" src="https://github.com/user-attachments/assets/334d82cc-ed70-4ea3-b61e-601a69889447"/>

### Result №1:

A dashboard that allows you to see the structure and dynamics of the performance of PhoneNow call center employees using three slicers:

- Period (January, February, March)
- Agent (Becky, Dan, Diane, Greg, Jim, Joe, Martha, Stewart)
- Topic (Admin Support, Contract related, Payment related, Streaming, Technical Support)

![screenshot-task-1-power-bi-practice](https://github.com/user-attachments/assets/92aaf657-a17b-46d7-a184-9c28a830ad05)

### Task №2:

Your colleague, the engagement partner, asks you to do the following tasks:
- Define proper KPIs
- Create a dashboard for the retention manager reflecting the KPIs
- Write a short email to him (the engagement partner) explaining your findings, and include suggestions as to what needs to be changed
  
![task_2](https://github.com/user-attachments/assets/66aa7c24-386d-47d3-b751-064363f2c23d)

### Result №2:

A dashboard that analyses the behaviour of a telecoms company's customers, dividing them into four categories depending on the presence of customer service tickets and churn:

- Customers who had tickets and churned
- Customers who had no tickets, but churned
- Customers who have tickets, but didn't churn
- Customers who have no tickets and didn't churn

The list of portraits indicates the priority of actions.

An example of the DAX formula used:

```DAX
Portrait's Contract = 

VAR CountMonth = COUNTROWS(FILTER('tickets - churn -', 'tickets - churn -'[Contract] = "Month-to-month"))

VAR CountYear = COUNTROWS(FILTER('tickets - churn -', 'tickets - churn -'[Contract] = "One year"))

VAR CountTwoYear = COUNTROWS(FILTER('tickets - churn -', 'tickets - churn -'[Contract] = "Two year"))

RETURN
     SWITCH(
     
          TRUE(),
          CountMonth >= CountYear && CountMonth >= CountTwoYear, "Month-to-month contract with an",
          CountYear >= CountMonth && CountYear >= CountTwoYear, "One year contract with an",
          CountTwoYear >= CountMonth && CountTwoYear >= CountYear, "Two year contract with an"
     
     )
```

![screenshot-task-2-power-bi-practice](https://github.com/user-attachments/assets/f816e263-e967-41e6-bd78-f9c7ca6ec498)

> Hi Janet,
>
> I'm back with the results of the analysis. The link to the dashboard is attached to the email.
>
> The dashboard analyses the behavior of PhoneNow customers, dividing them into four categories depending on the presence of customer service tickets and churn:
> 1. Customers who had tickets and churned.
> 2. Customers who had no tickets, but churned.
> 3. Customers who have tickets, but didn't churn.
> 4. Customers who have no tickets and didn't churn.
> 
> Each category has the demographic and account portrait of a majority of customers that represent it:
>
> 1. A young female who has a partner and doesn't have dependents. Uses a month-to-month contract with an average tenure of 32.85 months.
> 2. A young female who has a partner and doesn't have dependents. Uses a month-to-month contract with an average tenure of 8.48 months.
> 3. A young male who has a partner and doesn't have dependents. Uses a two-year contract with an average tenure of 50.59 months.
> 4. A young male who has a partner and doesn't have dependents. Uses a month-to-month contract with an average tenure of 36.9 months.
>   
> The list of portraits indicates the priority of actions. Clients in the first and second categories were at risk, so they changed service providers.
>
> So, for these two categories, it is necessary to review the quality of the most popular Internet services - Streaming movies and TV. In addition, analyze the main reasons for contacting the support service.
>
> Best regards,
>
> Dmytro

### Task №3:

Your task is to do the following:
- Define relevant KPIs in hiring, promotion, performance and turnover, and create a visualisation
- Write what you think some root causes of their slow progress might be

An example of the DAX formula used:

```DAX
% of turnover =

VAR __BASELINE_VALUE =

     COUNT('Pharma Group AG'[FY20 leaver?])

VAR __MEASURE_VALUE = 

     CALCULATE(

          COUNTA('Pharma Group AG'[FY20 leaver?]),
          'Pharma Group AG'[FY20 leaver?] IN { "Yes" }

     )

RETURN
     IF(

          NOT ISBLANK(__MEASURE_VALUE),
          DIVIDE(__MEASURE_VALUE, __BASELINE_VALUE)

     )
```

![task_3](https://github.com/user-attachments/assets/8d94c284-3d31-4dbf-a9d1-7fca1362c9f2)

### Result №3:

A basic visualizations that show the results of calculations needed for setting KPIs.

![screenshot-task-3-power-bi-practice](https://github.com/user-attachments/assets/8353163c-b325-4d39-9939-b92651a1e669)

> As we can see from the visualization, the average productivity for men and women is almost the same, which means that the problem is not in the results of work. However, subjective factors and biases in performance ratings that create systemic barriers can influence decisions about promotions or hiring. 

## What's next?

Despite mastering the most common Power BI functions, I see the need to deepen the practice of using more complex tools such as DAX formulas, as this allows you to make reports and calculations more informative.
