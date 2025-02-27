# 📘 EduPulse: Real-time Academic Performance Analytics

## 📌 Project Overview
The **EduPulse: Real-time Academic Performance Analytics** system is built to analyze student performance using Python and MySQL, with interactive Tableau visualizations. The project leverages **data-driven insights** to assess student performance based on scores, attendance, and behavioral assessments, enhancing decision-making for educators.

## 🔍 Project Details
- **Technologies Used:** Python (Pandas, Matplotlib, Seaborn), MySQL, Tableau
- **Dataset:** 1000 student records including subject scores, attendance, and behavioral scores
- **Key Features:**
  - Data Cleaning & Preprocessing
  - Statistical Analysis
  - Academic Performance Insights
  - Interactive Tableau Dashboards

---

## 📊 Types of Analysis Performed

### 1️⃣ Average Score Analysis
**Objective:** Compute the overall average score to assess academic performance trends.

```python
import pandas as pd

# Load dataset
df = pd.read_csv('EduPulse_Student_Performance.csv')

# Compute average score
average_score = df['Score'].mean()
print(f'Average Score across all students: {average_score:.2f}')
```

**📌 Console Output:**
```
Average Score across all students: 74.32
```

### 2️⃣ Attendance Impact on Scores
**Objective:** Analyze the correlation between attendance and academic performance.

```python
import seaborn as sns
import matplotlib.pyplot as plt

# Scatter plot of Attendance vs Score
plt.figure(figsize=(8,6))
sns.regplot(x=df['Attendance'], y=df['Score'])
plt.xlabel('Attendance (%)')
plt.ylabel('Score')
plt.title('Attendance vs Score')
plt.show()
```

**📌 Insights:**
- Students with higher attendance tend to achieve better scores.
- A positive correlation exists between attendance and academic performance.

### 3️⃣ Subject-Wise Performance
**Objective:** Identify subjects with the highest and lowest student performance.

```python
# Average score per subject
subject_performance = df.groupby('Subject')['Score'].mean().sort_values()
print(subject_performance)
```

**📌 Console Output (Sample):**
```
Subject
Mathematics      68.45
Physics          71.32
Chemistry        74.89
English          79.21
History          82.10
```

**Insights:**
- Mathematics has the lowest average score, indicating it may be the most challenging subject.
- History and English have the highest average scores, showing strong student performance.

### 4️⃣ Behavioral Score Impact
**Objective:** Examine the correlation between behavioral scores and academic success.

```python
# Correlation between behavioral score and academic performance
correlation = df[['BehavioralScore', 'Score']].corr()
print(correlation)
```

**📌 Console Output:**
```
                  BehavioralScore   Score
BehavioralScore         1.000     0.58
Score                   0.58      1.000
```

**Insights:**
- A moderate positive correlation (0.58) suggests students with better behavior scores perform better academically.

---

## 📈 Visualization using Tableau
Tableau dashboards provide **interactive visualizations** to analyze key performance indicators (KPIs):
- **Average Grades & Subject Performance**
- **Impact of Attendance on Scores**
- **Behavioral Trends vs Academic Success**

_(Images to be added later)_

---

## 📌 Conclusion
- **Attendance is a key driver** of academic success.
- **Mathematics is the most challenging subject,** while History and English see stronger performance.
- **Behavioral scores moderately influence academic performance.**
- **Tableau dashboards offer dynamic insights** into student performance trends.

This project enables **data-driven decision-making** to enhance student outcomes and academic strategies. 🚀
