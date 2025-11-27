# Mental-Health-Analysis-Dashboard
Mental health data analysis project using Python, SQL Server, and Power BI. Cleaned the data, stored it in a database, and built an interactive dashboard to understand stress, anxiety, and sleep patterns.

## 📂 Dataset

* File: `mental_health_data.csv` https://github.com/Shubhanshu007iit/Mental-Health-Analysis-Dashboard/blob/main/Mental_Health_Dataset.csv
* Columns include:
  `Age`, `Gender`, `Stress_Level`, `Anxiety_Score`, `Sleep_Hours`, `Department`, `Location`, `Date`

---

## 🚀 Project Workflow

## **1️⃣ Data Cleaning – Python**

I cleaned the dataset using Python to remove missing values, fix data types, and prepare it for SQL and Power BI.

### ✔ Python Code Example

```python
import pandas as pd

# Load dataset
df = pd.read_csv("mental_health_data.csv")

# Remove duplicates and missing values
df.drop_duplicates(inplace=True)
df.dropna(inplace=True)

# Convert data types
df["Stress_Level"] = df["Stress_Level"].astype(int)
df["Anxiety_Score"] = df["Anxiety_Score"].astype(int)
df["Sleep_Hours"] = df["Sleep_Hours"].astype(float)

# Format date column
df["Date"] = pd.to_datetime(df["Date"])

# Save cleaned file
df.to_csv("cleaned_data.csv", index=False)

print("Data Cleaning Completed!")
```

---

## **2️⃣ Store Data in SQL Server**

Imported the cleaned CSV into SQL using SQL Server Import Wizard.

### ✔ SQL Table Structure

```sql
CREATE TABLE MentalHealthData (
    ID INT IDENTITY(1,1) PRIMARY KEY,
    Age INT,
    Gender VARCHAR(20),
    Stress_Level INT,
    Anxiety_Score INT,
    Sleep_Hours FLOAT,
    Department VARCHAR(100),
    Location VARCHAR(100),
    Date DATE
);
```

### ✔ Sample SQL Queries Used

```sql
-- Check data
SELECT TOP 10 * FROM MentalHealthData;

-- Average stress & anxiety
SELECT 
    AVG(Stress_Level) AS Avg_Stress,
    AVG(Anxiety_Score) AS Avg_Anxiety
FROM MentalHealthData;

-- Department-wise stress
SELECT Department, AVG(Stress_Level) AS Avg_Stress
FROM MentalHealthData
GROUP BY Department;
```

---

## **3️⃣ Build Dashboard – Power BI**

Connected Power BI to SQL Server and created:

### ✔ Dashboard Visuals

* Average Stress, Anxiety, Sleep
* Stress Level Distribution
* Sleep vs Stress Scatter Plot
* Anxiety by Team/Department
* Age & Gender Breakdown
* Timeline Trends
* Filters: Date, Location, Department, Wellness Program

The dashboard helps understand how stress changes with sleep, age, gender, and work environment.

---

## 📸 Dashboard Preview

https://github.com/Shubhanshu007iit/Mental-Health-Analysis-Dashboard/blob/main/Dashboard%20Mental%20Health%20Analysis.png

:

```
![Dashboard](dashboard.png)
```

---

## 🛠️ Tech Stack

* **Python** – Pandas, NumPy
* **SQL Server**
* **Power BI**
* **Git & GitHub**

---

## 📁 Project Files

* `mental_health_data.csv` – original data
* `cleaned_data.csv` – cleaned data
* `data_cleaning.ipynb` – Python notebook
* `mental_health.sql` – SQL table + queries
* `dashboard.pbix` – Power BI report
* `README.md` – documentation

---

## 📜 Project Summary

I cleaned mental-health data using Python, saved it in SQL Server, and created a Power BI dashboard to understand how stress, anxiety, and sleep patterns affect different groups. This project helped me improve my data cleaning, SQL, and dashboard-building skills.

---

