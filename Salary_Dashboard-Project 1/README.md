# Excel Salary Dashboard

![Salary_Dashboard.png](../Images/Salary_Dashboard.png)

## Overview

This dashboard provides a comprehensive analysis of salaries for data-related roles, designed to assist job seekers in evaluating compensation for their desired positions. 

The underlying dataset is sourced from my Excel course, which focuses on foundational data analysis skills. The data includes job titles, salary figures, locations, and key skills, all of which are visualized and analyzed in this project.

### Dashboard File
The completed dashboard is available here: [Salary_Dashboard.xlsx](Salary_Dashboard.xlsx).

### Excel Skills Demonstrated

The following Excel features and techniques were applied:

- **📉 Charts**
- **🧮 Formulas and Functions**
- **❎ Data Validation**

### Dataset Description

The dataset comprises real-world data science job listings from 2023, featuring:

- **👨‍💼 Job Titles**
- **💰 Salaries**
- **📍 Locations**
- **🛠️ Skills**

## Dashboard Development

### 📉 Charts

#### 📊 Data Science Job Salaries - Bar Chart

<img src="/../Images/Salary_Dashboard_Chart1.png" width="850" height="550" alt="Salary Dashboard Chart1">

- 🛠️ **Excel Features:** Leveraged bar charts with formatted salary values and optimized layout for clarity.
- 🎨 **Design:** Horizontal bar chart to facilitate comparison of median salaries.
- 📉 **Data Organization:** Job titles sorted by descending salary for better readability.
- 💡 **Key Insights:** Highlights that senior and engineering roles command higher salaries compared to analyst positions.

#### 🗺️ Country Median Salaries - Map Chart

![Salary_Dashboard_Chart2.png](/../Images/Salary_Dashboard_Country_Map.gif)

- 🛠️ **Excel Features:** Used Excel's map chart to visualize median salaries by country.
- 🎨 **Design:** Color-coded map to distinguish salary levels across regions.
- 📊 **Data Representation:** Median salary plotted for each country with available data.
- 👁️ **Visual Enhancement:** Improved clarity and immediate understanding of geographic salary trends.
- 💡 **Key Insights:** Quickly reveals global salary disparities and highlights regions with the highest and lowest salaries.

### 🧮 Formulas and Functions

#### 💰 Median Salary by Job Title

```
=MEDIAN(
IF(
    (jobs[job_title_short]=A2)*
    (jobs[job_country]=country)*
    (ISNUMBER(SEARCH(type,jobs[job_schedule_type])))*
    (jobs[salary_year_avg]<>0),
    jobs[salary_year_avg]
)
)
```

- 🔍 **Multi-Criteria Filtering:** Filters by job title, country, schedule type, and excludes empty salary values.
- 📊 **Array Formula:** Utilizes `MEDIAN()` with a nested `IF()` for array analysis.
- 🎯 **Targeted Insights:** Delivers specific salary data by job title, region, and schedule type.
- **🔢 Purpose:** Populates the table below with the median salary based on selected criteria.

🍽️ Background Table

![Salary_Dashboard_Screenshot1.png](/../Images/Salary_Dashboard_Screenshot1.png)

📉 Dashboard Implementation

<img src="/../Images/Salary_Dashboard_Job_Title.png" width="400" height="500" alt="Salary Dashboard Title">

#### ⏰ Count of Job Schedule Type

```
=FILTER(J2#,(NOT(ISNUMBER(SEARCH("and",J2#))+ISNUMBER(SEARCH(",",J2#))))*(J2#<>0))
```

- 🔍 **Unique List Generation:** Uses the `FILTER()` function to exclude entries containing "and" or commas, and omits zero values.
- **🔢 Purpose:** Populates the table below with a unique list of job schedule types.

🍽️ Background Table

![1_Salary_Dashboard_Type.png](/../Images/Salary_Dashboard_Screenshot2.png)

📉 Dashboard Implementation:

<img src="/../Images/Salary_Dashboard_Type.png" width="350" height="500" alt="Salary Dashboard Type">

### ❎ Data Validation

#### 🔍 Filtered List

- 🔒 **Enhanced Data Validation:** Applied filtered lists as data validation rules for `Job Title`, `Country`, and `Type` fields in the Data tab to:
    - 🎯 Restrict user input to validated schedule types
    - 🚫 Prevent incorrect or inconsistent entries
    - 👥 Improve overall dashboard usability

<img src="/../Images/Salary_Dashboard_Data_Validation.gif" width="425" height="400" alt="Salary Dashboard Data Validation">

## Conclusion

This dashboard offers valuable insights into salary trends for various data-related roles. Built using data from my Excel course, it empowers users to make informed career decisions by exploring how location and job type impact compensation.
