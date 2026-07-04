# Data Science Job Market Analysis: The True Value of Skills


## Introduction
As a data science student looking for the best opportunities, I wanted to know which skills are the most valuable to learn. I created this project to see what skills top companies look for and how to get a higher salary.

### Questions to Analyze
To understand the job market, I asked four main questions:
1. **Do more skills get you better pay?**
2. **What is the salary for data jobs in different regions?**
3. **What are the top skills for data professionals?**
4. **How much do the top 10 skills pay?**

### Excel Skills Used
I used the following Excel tools to find the answers:
- **📊 Pivot Tables**
- **📈 Pivot Charts**
- **🧮 DAX (Data Analysis Expressions)**
- **🔍 Power Query**
- **💪 Power Pivot**

### Data Jobs Dataset
I used a dataset with real data science job postings from 2023. It includes details about:
- **👨‍💼 Job titles**
- **💰 Salaries**
- **📍 Locations**
- **🛠️ Skills**

## 1️⃣ Do more skills get you better pay?

### 🔍 Skill: Power Query (ETL)

#### 📥 Extract
- First, I used Power Query to pull data from the main file (`data_salary_all.xlsx`). I split it into two separate lists:
    - 🗃️ The first list contains all the main job information.
    - 🔧 The second list contains the skills for each specific job ID.

#### 🔄 Transform
- Next, I cleaned both lists. I changed the column data types, deleted columns I did not need, cleaned up text to remove words that were not useful, and removed empty spaces around the words.
    - 📊 data_jobs_all

        ![Cleaned Job Data](images/2_Project_Analysis_Screenshot1.png)

    - 🛠️ data_job_skills

        ![Cleaned Job Skills](images/2_Project_Analysis_Screenshot2.png)

#### 🔗 Load
- Finally, I loaded both clean lists back into my Excel workbook so they were ready for analysis.
    - 📊 data_jobs_all

        ![Loaded Job Data](images/2_Project_Analysis_Screenshot3.png)

    - 🛠️ data_job_skills

        ![Loaded Job Skills](images/2_Project_Analysis_Screenshot4.png)

### 📊 Analysis

#### 💡 Insights
- 📈 There is a positive connection between the number of skills in a job posting and the salary. This is especially true for roles like Senior Data Engineer and Data Scientist.
- 💼 Jobs that require fewer skills, like Business Analyst, usually pay less. This shows that knowing specialized skills brings higher value in the market.

    ![Skills vs Salary Chart](images/2_Project_Analysis_Chart1.png)

#### 🤔 So What
- This means it is highly valuable to learn multiple matching skills, especially if your goal is to move into higher-paying roles.

## 2️⃣ What’s the salary for data jobs in different regions?

### 🧮 Skills: PivotTables & DAX

#### 📈 Pivot Table
- 🔢 I created a PivotTable using the Data Model I built in Power Pivot.
- 📊 I placed the `job_title_short` column in the rows section and the `salary_year_avg` column in the values section.
- 🧮 Next, I added a new measure to find the middle (median) salary specifically for jobs in the United States:
    ```
    =CALCULATE(
        MEDIAN(data_jobs_all[salary_year_avg]),
        data_jobs_all[job_country] = "United States")
    ```

#### 🧮 DAX
- To calculate the median yearly salary for the whole dataset, I used this DAX formula:

    ```
    Median Salary := MEDIAN(data_jobs_all[salary_year_avg])
    ```

### 📊 Analysis

#### 💡 Insights
- 💼 High-level roles like Senior Data Engineer and Data Scientist get the highest median salaries both inside the United States and internationally. This shows a strong global demand for advanced data skills.
- 💰 There is a clear pay gap between roles in the US and roles outside the US. Salaries are noticeably higher in the US, which is likely because so many major tech companies are concentrated there.

    ![Salary by Region Chart](images/2_Project_Analysis_Chart2.png)

#### 🤔 So What
- These salary details are very important when planning your career or negotiating pay. They help both workers and companies set fair expectations based on where the job is located.

## 3️⃣ What are the top skills of data professionals?

### 🔧 Skill: Power Pivot

#### 💪 Power Pivot
- 🔗 I created a Data Model by bringing both the `data_jobs_all` and `data_jobs_skills` tables into one single system.
- 🧹 Since I had already cleaned the data using Power Query, Power Pivot made it easy to connect these two tables together.

#### 🔗 Data Model
- I created a relationship between my two tables using the `job_id` column to connect them.

    ![Power Pivot Data Model](images/2_Project_Analysis_Screenshot5.png)

#### 📃 Power Pivot Menu
- I used the Power Pivot menu to organize my data model and easily create my calculated measures.

    ![Power Pivot Menu](images/2_Project_Analysis_Screenshot6.png)

### 📊 Analysis

#### 💡 Insights
- 💻 SQL and Python are the most popular skills in data jobs. This shows they are the absolute foundation for working with data.
- ☁️ Cloud technologies like AWS and Azure also appear frequently, which proves that the industry is heavily moving toward cloud services and big data tools.

    ![Top Skills Chart](images/2_Project_Analysis_Chart3.png)

#### 🤔 So What
- Knowing which skills are the most popular helps professionals stay competitive. It also shows beginners exactly which technologies they should study first to match what companies want.

## 4️⃣ What’s the pay of the top 10 skills?

### 📊 Skill: Advanced Charts (Pivot Chart)

#### 📈 PivotChart
- I created a combo PivotChart to show both the median salary and how common each skill is (skill likelihood %) from my PivotTable.
    - 🪙 **Primary Axis:** Median Salary (shown as vertical Bars).
    - 👍 **Secondary Axis:** Skill Likelihood (shown as a Line with Diamond markers).
- To make the chart look clean, I added clear axis titles, removed the default gridlines, and customized the markers.

### 📊 Analysis

#### 💡 Insights
- 💰 Higher salaries are tied directly to skills like Python, Oracle, and SQL. This proves that these technologies are critical for landing high-paying tech roles.
- 📉 Basic tools like PowerPoint and Word have the lowest median salaries and are rarely requested, showing they do not add specialized value in high-salary sectors.

    ![Salary vs Likelihood for Top 10 Skills](images/2_Project_Analysis_Chart4.png)

### 🤔 So What
- This chart clearly shows that if you want to maximize your salary in the data industry, you should invest your time in learning high-value technical skills like Python and SQL rather than basic office software.

## Conclusion

I built this project to explore the reality of the data science job market using real-world job postings. By using Excel features like Power Query to clean the data, Power Pivot to manage the large dataset, and PivotTables with DAX to calculate exact figures, I uncovered clear trends. 

The data proves that specialized technical skills , especially Python, SQL, and cloud technologies are directly connected to fewer competitors and much higher pay. I hope this project serves as a clear, practical guide for anyone looking to build a successful and high-paying career in data!