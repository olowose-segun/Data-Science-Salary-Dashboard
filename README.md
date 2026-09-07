# Data Science Salary Dashboard
>This started as a course project, but turned into something I'm genuinely proud of. I built a Data Jobs Salary Dashboard to help job seekers check whether they're being paid fairly for their role, and along the way I learned a ton about charts, formulas, and data validation in Excel.

## 📑**Intro**
This one started as a course project, but turned into something I'm genuinely proud of. I built a Data Jobs Salary Dashboard to help job seekers check whether they're being paid fairly for their role, and along the way I learned a ton about charts, formulas, and data validation in Excel.

## 🌐**Data Source**
The data used for this analysis was sourced from the tutorial files provided in *Luke Barousse’s Excel for Beginners* course [here](https://github.com/lukebarousse/Excel_Data_Analytics_Course/tree/main)

## 🛠️**Tools Used**
- Excel - (Data Cleaning, Charts, Formulas & Functions, Dashboard Implementation and KPI Cards)

## 📊**Exploratory Data Analysis**
1. What are the top 10 highest-paying jobs based on salary?
2. Is data analysis still a lucrative career skill to learn, and does it rank among the top 10 highest-paying jobs?
3. Which country offers the highest salaries for data scientists across different job schedules?
4. What is the most popular recruiting platform in the United States?
5. What are the five highest-paying roles in the United States?


## 📊**Data Analysis**
- Extracting & Counting Job Titles
  <img width="1116" height="571" alt="Screenshot 2026-09-05 181116" src="https://github.com/user-attachments/assets/ea0ac8bd-0009-440a-8e19-48a3396e1520" />


- Calculating Median Salary per Job Title
  <img width="1119" height="556" alt="Screenshot 2026-09-05 182921" src="https://github.com/user-attachments/assets/59a376b5-2bf0-48e6-93a5-7412033173a9" />


- Pulling the Country List
  <img width="755" height="653" alt="Screenshot 2026-09-05 201706" src="https://github.com/user-attachments/assets/89acbf76-bd5d-45b6-90bf-de2f392b4361" />

- Cleaning Up the Schedule Types
<img width="283" height="136" alt="Screenshot 2026-09-07 013959" src="https://github.com/user-attachments/assets/e7008481-fa9f-4ffa-9920-9a49227e7732" />

  
- Country Validation & Median Salary
- I calculated the median salary per country:
  <img width="743" height="336" alt="Screenshot 2026-09-07 014134" src="https://github.com/user-attachments/assets/38cdb640-c61c-41b1-bfe6-839d6ac1f39d" />
  `=MEDIAN(IF(jobs[job_country]=A2,(jobs[salary_year_avg]<>0)*(jobs[salary_year_avg])))`

  Then layered in job title and schedule type so the numbers get more specific:

  `=MEDIAN(
  IF(
  (jobs[job_country]=A2)*(jobs[salary_year_avg]<>0)*
  (jobs[job_title_short]=title)*
  (ISNUMBER(SEARCH(type,jobs[job_schedule_type]))),
  (jobs[salary_year_avg])))`
  I had a few `#NUM!` errors pop up so I filtered those out and sorted by median salary:
  `=SORT(FILTER(A2:B112,ISNUMBER(B2:B112)),2,-1)`

- I calculated for median salary by Job Type
<img width="648" height="164" alt="Screenshot 2026-09-07 015107" src="https://github.com/user-attachments/assets/836d5f58-ef74-4159-8809-4d924e9437fa" />

- I also calculated for the top jobs platform and counts of jobs per platform and country
  `=COUNT(
IF(
(jobs[job_country]=country)*
(jobs[job_title_short]=title)*
(ISNUMBER(SEARCH(type,jobs[job_schedule_type])))*
(jobs[job_via]=A2),
jobs[salary_year_avg]))`
- I used map charts and bar charts to visualize my results
  <img width="572" height="334" alt="Screenshot 2026-09-05 222658" src="https://github.com/user-attachments/assets/f38308ff-82ab-4c10-a882-44981c09f93d" />
<img width="526" height="331" alt="Screenshot 2026-09-05 220335" src="https://github.com/user-attachments/assets/7aeaee05-0838-48c2-bea6-dd5b82a72024" />
<img width="601" height="342" alt="Screenshot 2026-09-05 220324" src="https://github.com/user-attachments/assets/9ac0da32-3d6c-4c52-b92d-a3424f2aceea" />

- I created KPI Cards (median salary, top job platform and job counts)
  <img width="1810" height="166" alt="Screenshot 2026-09-07 014802" src="https://github.com/user-attachments/assets/c47664ed-841c-43a7-8761-664ebbc118b0" />
- After completing the analysis and visualizations, I standardized the dashboard formatting, including colors, titles, dimensions, outlines, and other visual elements.

To preserve the integrity of the analysis, I protected the worksheet and restricted editing to three validated input cells; **Job Title, Job Country, and Job Schedule Type**.


### This is what the final dashboard looks like
<img width="1893" height="713" alt="Screenshot 2026-09-06 103210" src="https://github.com/user-attachments/assets/0571db17-d7ca-47a3-8f2b-05d0734c703e" />


## 🔖**Results & Observations**
- The following are the top 10 highest-paying positions; business analyst, cloud engineer, data analyst, data engineer, data scientist, machine learning engineer, senior data analyst, senior data engineer, senior data scientist and software engineer.
- Yes, data analysis is a lucrative career skill, as it ranks among the top 10 highest-paid roles.
- The United States is the highest-paying country for Data Scientists across all work schedules.
- ***Indeed*** is the top job application platform for Data Analysts, with over 6,000 job postings in the United States.
- The top 5 highest-paying roles in the United States are; Senior Data Scientist, Senior Data Engineer, Machine Learning Engineer, Data Scientist, and Data Engineer.

## 💡**Conclusion**
- Based on the findings, data analytics continues to be a financially rewarding career path, ranking within the top 10 highest-paying skills in data science.

## 📜**References and Credits**
- This project is inspired by and credited to Luke Barousse, who was the first person I learned Excel from. His course gave me the foundation I needed to carry out this analysis and put my skills into practice. Big credit to Luke for the knowledge and guidance. You can check out his Excel course [here](https://www.youtube.com/watch?v=pCJ15nGFgVg)

