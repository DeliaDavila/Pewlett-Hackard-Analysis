# Pewlett Hackard Analysis

## Overview of Project
### Purpose
This project was done to help Pewlett Hackard understand and prepare for a large wave of retirements in the near future. I helped the company understand the problem by creating materials showing concrete numbers of employees eligible to retire and the titles held by those employees. 
### Planning
To help the company prepare for the possible retirements, I created a list of employees to begin recruiting for a mentorship program where the retirement-eligible employees would have the option of phasing into retirement with part-time work mentoring the next wave of employees to take over their positions.

## Results
### Overview of retirements
The file *retirement_titles.csv* shows all employees with eligible birthdates. 
* When filtered for current employees only, the number of current employees who might retire is over 70,000.
* Reviewing the “from_date”, which indicates the amount of time in these titles, the vast majority of the eligible retirees have decades of experience in their roles.

![PossibleRetirements](https://github.com/DeliaDavila/Pewlett-Hackard-Analysis/blob/main/Images/PossibleRetirements.png)

### Overview of titles
The file *retiring_titles.csv* shows the number of possible retirements are shown by job title.
* The distribution of retirements is uneven. Some titles will be more affected by retirements.
* Both titles with more than 20,000 possible retirements are Senior level, indicating significant experience and knowledge.

![RetiringTitles](https://github.com/DeliaDavila/Pewlett-Hackard-Analysis/blob/main/Images/RetiringTitles.png)

## Summary
Pewlett Hackard is facing a "silver tsunami", a large wave of employees who will be eligible to retire around the same time. I looked at the data to review the situation and answer questions around the issue, covered in the sections below. I will also make additional recommendations.

### Size of effect
The question to answer is: How many roles will need to be filled as the "silver tsunami" begins to make an impact?
To answer this question, I queried the "retirement_titles" table for a count of employees with the placeholder date of 1/1/9999. This gives the total number of current employees who will be eligible to retire: 72,458.

```
SELECT COUNT(emp_no)
FROM retirement_titles
WHERE to_date = '9999-01-01';
```

From this, we see that the potential impact will be very large. Given the seniority and years of experience of the employees who may retire, it is necessary to begin mitigating the impact of those retirements. The suggestion of creating a mentorship program is, in my opinion, a necessary step. This will allow for an interim "semi-retirement" to slow the exit of experienced employees and allow them to stay involved with the company with reduced hours. The institutional knowledge can then be passed down to other employees before a full retirement begins.


### Change management
The question to answer here is: Are there enough qualified, retirement-ready employees in the departments to mentor the next generation of Pewlett Hackard employees?

The answer to this question is, unfortunately, it depends. As seen in the "retiring titles" table, some areas have large numbers of experienced employees who can pass down knowledge.

![RetiringTitles](https://github.com/DeliaDavila/Pewlett-Hackard-Analysis/blob/main/Images/RetiringTitles.png)

However, the number of retiring managers is only 2. This leaves open the possibility for loss of knowledge and I recommend that additional steps are taken.

### Recommendations
The small number of managers who might retire might not be a major issue, if their expertise can be duplicated from outside sources or if there is significant overlap in their specialized knowledge. I recommend further analysis of the manager's history to investigate what departments might not have duplicate knowledge. To do this, I would create a report showing the previous titles and departments of all managers, retiring and remaining, to get a sense of how much institutional knowledge is part of the manager role. This will also help determine if there is overlap with the current managers. 

To prepare for a potential management training program, I suggest some additional analysis of current employees to investigate which departments or titles might lack enough employees to recruit into senior or management roles. I recommend initiating the mentorship program between retiring and senior employees, but then adding additional stages where the senior employees also act as mentors to more junior employees. This solves the issue of retirements in the future as well.





