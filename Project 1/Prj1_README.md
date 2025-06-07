# Excel Salary Dashboard

![Dashboard](/Resources/image/Dashboard.png)

## Introduction

This data jobs salary dashboard was created to help job seekers investigate salaries for their desired jobs and ensure they are being adequately compensated. 

The data is from my Excel course, which provides a foundation in analyzing data using this powerful tool. The data contains detailed information on job titles, salaries, locations, and essential skills that are presented here.

### Dashboard File
My final dashboard is in [Project_1_Salary_Dashboard.xlsx](Project_1_Salary_Dashboard.xlsx).

### Excel Skills Used

The following Excel skills were utilized for analysis:

- **📉 Charts**
- **🧮 Formulas and Functions**
- **❎ Data Validation**

### Data Jobs Dataset

The dataset used for this project contains real-world data science job information from 2023. The dataset is available via my Excel course, which provides a foundation for analyzing data using Excel. It includes detailed information on:

- **👨‍💼 Job titles**
- **💰 Salaries**
- **📍 Locations**
- **🛠️ Skills**

## Dashboard Build

### 📉 Charts

#### 📊 Data Science Job Salaries - Bar Chart

![data_science_job_salary](/Resources/image/Dashboard.png)

- 🛠️ **Excel Features:** Utilized bar chart feature (with formatted salary values) and optimized layout for clarity.
- 🎨 **Design Choice:** Horizontal bar chart for visual comparison of median salaries.
- 📉 **Data Organization:** Sorted job titles by descending salary for improved readability.
- 💡 **Insights Gained:** This enables quick identification of salary trends, noting that Senior roles and Engineers are higher-paying than Analyst roles.

### 🧮 Formulas and Functions

#### 💰 Median Salary by Job Titles

```
= MEDIAN
(
IF(
    (A2=jobs[job_title_short])*
    (jobs[salary_year_avg]<>0)*
    (jobs[job_country]=ctry)*
    (ISNUMBER(SEARCH(DASHBOARD!$O$4,jobs[job_schedule_type]))),
jobs[salary_year_avg],"No Result")
)
```

- 🔍 **Multi-Criteria Filtering:** Checks job title, country, schedule type, and excludes blank salaries.
- 📊 **Array Formula:** Utilizes `MEDIAN()` function with nested `IF()` statement to analyze an array.
- 🎯 **Tailored Insights:** Provides specific salary information for job titles, regions, and schedule types.
- **🔢 Formula Purpose:** This formula populates the table below, returning the median salary based on job title, country, and type specified.

🍽️ Background Table

![data_job_salary_table](/Resources/image/data_job_salary_table.png)

📉 Dashboard Implementation

![1_Salary_Dashboard_Job_Title](/Resources/image/1_Salary_Dashboard_Job_Title.png)

#### ⏰ Count of Job Schedule Type

```
= FILTER(A2#,NOT(ISNUMBER(SEARCH("and",A2#)))*(A2#<>0))
```

- 🔍 **Unique List Generation:** This Excel formula below employs the `FILTER()` function to exclude entries containing "and" or commas, and omit zero values.
- **🔢 Formula Purpose:** This formula populates the table below, which gives us a list of unique job schedule types.

🍽️ Background Table

![job_type.png](/Resources/image/job_type.png)

📉 Dashboard Implementation:

![2_job_type_count.png](/Resources/image/2_job_type_count.png)

### ❎ Data Validation

#### 🔍 Filtered List

- 🔒 **Enhanced Data Validation:** Implementing the filtered list as a data validation rule under the `Job Title`, `Country`, and `Type` option in the Data tab ensures
    - 🎯 User input is restricted to predefined, validated schedule types

    - 🚫 Incorrect or inconsistent entries are prevented

    - 👥 Overall usability of the dashboard is enhanced

![job_data_validation.png](/Resources/image/job_data_validation.png)

## CONCLUSION

🎯 I created this dashboard to showcase insights into salary trends across various data-related job titles. Utilizing data from my Excel course, this dashboard allows users to make informed decisions about their career paths. Exploring the functionalities to understand how location and job type influence salaries.