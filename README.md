# pupil-premium-performance
Data analysis project exploring Pupil Premium attainment using SQL and Excel

# 📊 Pupil Premium Performance: A Data Analysis of Year 7 Attainment

This project explores attainment outcomes for Pupil Premium (PP) pupils in a Year 7 mathematics class. Using real anonymised classroom data, I used SQL and Excel to investigate performance differences, identify at-risk learners, and visualize trends across key metrics such as attendance and behaviour.

---

## 📁 Datasets Used

- `student_profiles.csv`  
  Contains:  
  - Pupil Premium status  
  - Attendance (%)  
  - Behaviour Points  
  - AP1 Maths Assessment Scores  
  - SEN status  

---

## 🎯 Project Goals

- Compare average maths scores between PP and non-PP students  
- Examine the relationship between attendance and attainment  
- Explore behaviour patterns in relation to scores  
- Identify students who may require academic intervention  

---

## 🧮 SQL Analysis

### Average Score by Pupil Premium Status
```sql
SELECT PP, AVG(AP1_Score) AS Average_AP1_Score
FROM student_profiles
GROUP BY PP;
```

### Attendance vs Attainment
```sql
SELECT Attendance, AP1_Score
FROM student_profiles;
```

### Behaviour vs Attainment
```sql
SELECT BehaviourPoints, AP1_Score
FROM student_profiles;
```

### Identify At-Risk PP Students
```sql
SELECT * FROM student_profiles
WHERE PP = 'Yes' AND AP1_Score < 30 AND Attendance < 90;
```

---

📊 Visual Insights

- **Bar Chart:** Average AP1 scores by PP status  
- **Scatter Plot:** Attendance vs AP1 Score  
- **Scatter Plot:** Behaviour Points vs AP1 Score  
- **Table:** PP students at risk based on multiple indicators

*All visuals created in Excel using data exported from SQL queries.*

---

🔍 Key Findings

- PP students scored an average of **~7 points lower** than non-PP students on AP1.
- **Low attendance** (below 90%) was strongly linked to lower scores.
- **High negative behaviour points** correlated with reduced attainment.
- **Two PP students** were flagged as high risk based on a combination of attendance, score, and behaviour.

---

 ✅ Conclusion

This project demonstrates how data analytics can uncover important trends in pupil performance and inform evidence-based intervention strategies. Using simple tools like SQL and Excel, we can support educators in making equitable decisions grounded in data.

---
Future Enhancements

- Add post-intervention data to assess impact  
- Create a Power BI dashboard  
- Expand dataset to other subjects or year groups  
- Automate SQL reporting into visual dashboards

---
**Author**: [Aliyah Islam]  
**Data Source**: Anonymised PGCE placement classroom data

