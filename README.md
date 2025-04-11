# 🚀 Job Data Analytics Dashboard

This project is a comprehensive Power BI dashboard that visualizes insights from a job listings dataset based on multiple advanced filtering conditions. It showcases different analytical charts and enforces time-based visibility logic for secure and context-aware display.

---

## 📊 Features

### 1. **Top 10 Companies Hiring for Data Engineering & Data Scientist Roles**
- Filters:
  - Non-Asian countries only.
  - Country name should not start with ‘C’.
  - Latitude must be above 10.
  - Preference: Female.
  - Qualification: B.Tech.
  - Job Posting Date: Between 01/01/2023 and 06/01/2023.
- **Chart Visibility:** Only between **3 PM to 5 PM IST**.
- **Chart Type:** Bar Chart.
- **X-Axis:** Company Name  
- **Y-Axis:** Count of Job Roles  

---

### 2. **Country-Wise Role Distribution for Data Scientist, Art Teacher, Aerospace Engineer**
- Filters:
  - Countries: India (orange), Germany (green).
  - Qualification: B.Tech.
  - Experience: >2 years.
  - Salary: > $10k.
  - Job Portal: Indeed.
  - Preference: Female.
  - Work Type: Full Time.
  - Job Posting Date: < 08/01/2023.
- **Chart Visibility:** Only between **3 PM to 5 PM IST**.
- **Chart Type:** Column or Clustered Bar Chart.  
- **Legend:** Country Color  
- **X-Axis:** Job Title  
- **Y-Axis:** Number of Positions  

---

### 3. **Top 5 Roles in 2023 for Account Director (Internship)**
- Filters:
  - Work Type: Intern.
  - Job Title: Account Director.
  - Company Size: Below 2M.
- **Chart Type:** Bar Chart / Treemap.
- **X-Axis:** Role.
- **Y-Axis:** Count.

---

## 🛠️ Tech Stack

- **Power BI Desktop** – for data modeling, transformation, and visualization.
- **Power Query Editor** – for data preprocessing and filter logic.
- **DAX** – for calculated columns and dynamic time visibility logic.
- **GitHub** – version control and repository hosting.
- **[Deployed Frontend Link](#)** – hosted on Vercel / Netlify.
- **[Deployed Backend/API (if applicable)](#)** – hosted on Render / Railway.

---

## ⏰ Time-Based Visibility Logic (DAX Snippet)

```DAX
ShowChart = 
VAR CurrentTime = NOW() + TIME(5,30,0)  -- Adjusting UTC to IST
VAR Hour = HOUR(CurrentTime)
RETURN IF(Hour >= 15 && Hour < 17, 1, 0)
