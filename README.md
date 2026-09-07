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
5. What is the distribution of data science job opportunities across different countries?

## 📊**Data Analysis**
- Extracting & Counting Job Titles
  
- Calculating Median Salary per Job Title
- Pulling the Country List
- Cleaning Up the Schedule Types
- Country Validation & Median Salary - I calculated the median salary per country:
  
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
- I used map charts and bar charts to visualize my results
- I calculated for median salary by Job Type


