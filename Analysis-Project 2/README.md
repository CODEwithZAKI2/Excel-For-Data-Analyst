# Analysis - Project 2

## Overview

Despite the rapid growth of the data science field, there is limited data-driven insight into which jobs and skills are most valuable. This project aims to identify the skills top employers seek and how these skills impact salary potential.

### Key Questions Explored

To better understand the data science job landscape, this analysis addresses:

1. **Does possessing more skills lead to higher pay?**
2. **How do salaries for data roles vary by region?**
3. **Which skills are most in-demand among data professionals?**
4. **What are the salary trends for the top 10 skills?**

### Excel Techniques Applied

The following Excel features were essential for this analysis:

- **📊 Pivot Tables**
- **📈 Pivot Charts**
- **🧮 DAX (Data Analysis Expressions)**
- **🔍 Power Query**
- **💪 Power Pivot**

### About the Dataset

The dataset comprises real-world data science job listings from 2023, including:

- **👨‍💼 Job titles**
- **💰 Salaries**
- **📍 Locations**
- **🛠️ Required skills**

---

## 1️⃣ Does Having More Skills Increase Your Pay?

### 🔍 Power Query (ETL Process)

#### 📥 Extract

- Used Power Query to import the original data (`data_salary_all.xlsx`) and created two queries:
    - 🗃️ One containing all job information.
    - 🔧 Another listing skills for each job ID.

#### 🔄 Transform

- Cleaned and transformed the data by adjusting column types, removing unnecessary columns, standardizing text, and trimming whitespace.

    - 📊 data_jobs_all

        ![Project_Analysis_Screenshot1.png](../Images/Project_Analysis_Screenshot1.png)

    - 🛠️ data_job_skills

        ![Project_Analysis_Screenshot2.png](../Images/Project_Analysis_Screenshot2.png)

#### 🔗 Load

- Loaded the transformed queries into the workbook to enable further analysis.

    - 📊 data_jobs_all

        ![Project_Analysis_Screenshot3.png](../Images/Project_Analysis_Screenshot3.png)

    - 🛠️ data_job_skills

        ![Project_Analysis_Screenshot4.png](../Images/Project_Analysis_Screenshot4.png)

### 📊 Analysis & Insights

- 📈 There is a clear positive relationship between the number of skills required and median salary, especially for roles like Senior Data Engineer and Data Scientist.
- 💼 Positions requiring fewer skills, such as Business Analyst, tend to offer lower salaries, highlighting the premium on specialized expertise.

    ![Project_Analysis_Chart1.png](../Images/Project_Analysis_Chart1.png)

**Takeaway:**  
Acquiring a broader set of relevant skills can significantly boost earning potential, especially for those targeting senior roles.

---

## 2️⃣ How Do Data Job Salaries Differ by Region?

### 🧮 PivotTables & DAX

#### 📈 Pivot Table

- Built a PivotTable using the Power Pivot Data Model.
- Placed `job_title_short` in rows and `salary_year_avg` in values.
- Added a DAX measure to calculate the median salary for US-based jobs:
    ```
    =CALCULATE(
        MEDIAN(data_jobs_all[salary_year_avg]),
        data_jobs_all[job_country] = "United States")
    ```

#### 🧮 DAX

- Used DAX to compute the overall median salary:
    ```
    Median Salary := MEDIAN(data_jobs_all[salary_year_avg])
    ```

### 📊 Analysis & Insights

- 💼 Senior Data Engineer and Data Scientist roles offer the highest median salaries both in the US and globally, reflecting strong demand for advanced data skills.
- 💰 The salary gap between US and non-US roles is most pronounced in high-tech positions, likely due to the concentration of tech industries in the US.

    ![Project_Analysis_Chart2.png](../Images/Project_Analysis_Chart2.png)

**Takeaway:**  
Understanding regional salary trends is crucial for both job seekers and employers to make informed decisions and negotiate effectively.

---

## 3️⃣ What Are the Top Skills for Data Professionals?

### 🔧 Power Pivot

#### 💪 Data Modeling

- Integrated `data_jobs_all` and `data_jobs_skills` tables into a unified data model.
- Established a relationship between tables using the `job_id` column.

    ![Project_Analysis_Screenshot5.png](../Images/Project_Analysis_Screenshot5.png)

#### 📃 Power Pivot Menu

- Utilized the Power Pivot menu to refine the data model and streamline measure creation.

    ![Project_Analysis_Screenshot6.png](../Images/Project_Analysis_Screenshot6.png)

### 📊 Analysis & Insights

- 💻 SQL and Python are the most sought-after skills, underscoring their importance in data processing and analytics.
- ☁️ Cloud technologies like AWS and Azure are increasingly in demand, reflecting the industry’s shift toward cloud-based solutions.

    ![2_Project_Analysis_Chart3.png](/../Images/Project_Analysis_Chart3.png)

**Takeaway:**  
Staying current with in-demand skills such as SQL, Python, and cloud platforms is essential for career growth in data science.

---

## 4️⃣ What’s the Pay for the Top 10 Skills?

### 📊 Advanced Charting (Pivot Chart)

#### 📈 Combo PivotChart

- Created a combo PivotChart to visualize both median salary and skill likelihood (%):
    - 🪙 **Primary Axis:** Median Salary (Clustered Column)
    - 👍 **Secondary Axis:** Skill Likelihood (Line with Markers)
- Customized the chart with axis titles and diamond markers for clarity.

### 📊 Analysis & Insights

- 💰 Skills like Python, Oracle, and SQL are linked to the highest median salaries, highlighting their value in the tech sector.
- 📉 Skills such as PowerPoint and Word are associated with lower salaries and demand, indicating less relevance for high-paying data roles.

    ![Project_Analysis_Chart4.png](../Images/Project_Analysis_Chart4.png)

**Takeaway:**  
Investing in high-value skills like Python and SQL can significantly enhance earning potential in data science.

---

## Conclusion

This Excel-based project provides actionable insights into the data science job market using real-world job postings. By leveraging advanced Excel features—Power Query, PivotTables, DAX, and data visualization—I uncovered key relationships between skills and salaries. The findings highlight the importance of continuous skill development, especially in Python, SQL, and cloud technologies, for those aiming for top-tier roles in data science.

I hope this analysis serves as a valuable resource for data professionals seeking to advance their careers and for organizations aiming to stay competitive in the evolving tech landscape.
