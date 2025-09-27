# 📊 Insurance Charges Analysis Across Demographics (Power BI Project)

## 📌 Project Overview
This project explores **insurance charges across different demographics in the USA**, using a dataset from **Kaggle**.  
The main goal was to understand **how age, BMI, smoking habits, and lifestyle factors affect medical insurance charges**, and to identify opportunities to reduce per-head expenses.

The analysis and insights were built in **Power BI**, combining **data cleaning, DAX transformations, and storytelling dashboards**.

---

## 🗂 Dataset
- **Source:** [Kaggle – Medical Insurance Dataset](https://www.kaggle.com/datasets/mirichoi0218/insurance)  
- **Total Records:** `1,338 individuals`  
- **Key Columns:**  
  - `age` – Age of individual  
  - `bmi` – Body Mass Index (a measure of body fat)  
  - `charges` – Medical insurance charges incurred  
  - `smoker` – Smoking status (Yes/No)  
  - `region` – Region of residence (US)  
  - `children` – Number of dependents  

- **Data Preparation:**  
  - Verified dataset had no missing/null values  
  - Formatted BMI to **2 decimal places**  
  - Rounded Charges to **0 decimals** for readability  

---

## 🛠 Data Transformation & DAX
Two calculated columns were created following **WHO guidelines**:

### 1. Age Group Classification
```DAX
Age Group = SWITCH(TRUE(),
    insurance[age] <= 29, "Young Adult",
    insurance[age] <= 44, "Early Middle Age",
    insurance[age] <= 59, "Late Middle Age",
    "Senior"
)
```

### 2. BMI Category Classification
*(BMI: measure of body fat based on height & weight)*  
```DAX
BMI Category = SWITCH(TRUE(),
    insurance[bmi] < 18.5, "Underweight",
    insurance[bmi] <= 24.9, "Normal Weight",
    insurance[bmi] <= 29.9, "Over Weight",
    "Obese"
)
```

---

## 📈 Key Insights & Storytelling
### 🔹 Age vs Charges
- **Seniors** incur **~50% higher average charges** compared to Young Adults.  
- Charges increase steadily with age as BMI also trends upward.

### 🔹 Age vs BMI
- **Young Adults** → Lowest median BMI (29.8)  
- **Seniors** → Highest median BMI (32.2)  
- Suggests lifestyle and stress may contribute to increasing BMI with age.

### 🔹 BMI vs Charges
- **Obese individuals** consistently incur the **highest charges**.  
- **Underweight individuals** face the **lowest insurance costs**.  

### 🔹 Smoking Impact
- **Senior & Overweight group** → ~40% smokers.  
- **Early Middle Age & Underweight group** → Highest smoking ratio (~60%).  
- **Non-smokers reduce charges by ~33%**.  
- In some groups, quitting smoking can cut charges by **56%**.  

---

## 📊 Visual Highlights
The Power BI report uses dashboards to illustrate:  
1. Average charges distribution across age groups  
2. Median BMI trend vs age  
3. Charges distribution by BMI categories  
4. Smoking impact on insurance charges  

📸 Screenshots are available in the `/images` folder.

---

## 📂 Repository Structure
```
📁 Insurance-Charges-Analysis
 ┣ 📄 README.md               ← Detailed project documentation
 ┣ 📄 Insurance_Report.pdf     ← Polished PDF report with insights
 ┗ 📁 images/                  ← Power BI dashboard screenshots
```

---

## 🚀 How to Use
- **Stakeholders:**  
  - View the [Insurance_Report.pdf](./Insurance_Report.pdf) for insights.  
  - Browse `/images` folder for dashboard screenshots.  

---

## 🎯 Business Takeaways
- Insurance charges are **heavily impacted by lifestyle factors** (BMI & smoking).  
- Preventive health measures (quitting smoking, weight management) could significantly reduce charges.  
- Policy adjustments may target **high-risk groups** (Seniors, Obese, Smokers).  

---

## 🙌 Credits
- **Prepared by:** *Idamin Rahaman*  
- **Tools Used:** Power BI, DAX  
- **Dataset:** Kaggle (Medical Insurance Dataset)  

---
