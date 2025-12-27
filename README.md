**Clinical Operations Analytics Using MIMIC-IV**

## **Project Overview**

This project analyzes hospital and ICU clinical operations data from the **MIMIC-IV demo dataset** to understand how **care intensity, monitoring burden, and length of stay** relate to patient outcomes.

The objective is not clinical prediction, but **operational insight**, translating clinical data into **actionable signals for hospital systems and clinical decision support applications**.

---

clinical_operations_EDA_MIMIC/
│
├── data/
│   └── features_admission_level.csv            # Dataset used for analysis
│
├── notebooks/
│   └── clinical_operations_EDA.ipynb       # jupyter notebook with EDA 
│   
├── plots/
│   └── monitoring_intensity_vs_mortality.png  # Key operations insights and findings
│   └── los_vs_mortality.png
└── README.md                      # Project documentation
---

## **Business Context**

Hospitals and clinical decision support platforms need to:

* Identify high-risk admissions early  
* Optimize ICU utilization  
* Reduce unnecessary length of stay  
* Allocate staff and monitoring resources efficiently

This analysis explores whether **routine operational signals** (monitoring intensity, ICU admission, LOS) can act as **early indicators of risk and cost concentration**.

---

## **Data Sources**

* **MIMIC-IV (Demo)** — de-identified clinical dataset  
* Tables used:  
  * `patients`  
  * `admissions`  
  * `icustays`  
  * `chartevents` (sampled)  
  * `prescriptions`

All analysis is performed at the **hospital admission level**.

---

## **Key Hypotheses**

1. ICU-admitted patients experience longer hospital stays.  
2. Higher clinical monitoring intensity is associated with increased mortality risk.  
3. Patients who die in hospital have longer lengths of stay.  
4. Abnormal clinical signals are associated with medication escalation.  
5. ICU care increases resource utilization but is essential for high-risk patients.

---

## **Key Metrics Engineered**

* Hospital length of stay (mean & median)  
* ICU admission flag  
* ICU length of stay  
* Vital-sign monitoring intensity  
* Unique vitals measured  
* In-hospital mortality flag

---

## **Key Findings & Insights**

### **1️⃣ ICU Admission & Length of Stay**

* **ICU patients stay significantly longer** in hospital than non-ICU patients.  
* ICU admission is associated with higher clinical complexity and resource use.


| ICU\_admission\_flag | Mean LOS |
| :---- | :---- |
| 0 | \~5 |
| 1 | 9 |


**Operational Insight:**  
ICU beds are predominantly occupied by longer-stay, high-complexity patients.

---

### **2️⃣ Monitoring Intensity & Mortality**

* Patients with **extremely high monitoring intensity** show **substantially higher mortality rates**.  
* High-intensity monitoring patients represent a **smaller but high-risk group**.

| Monitoring intensity group | Mortality rate |
| :---- | :---- |
| Moderate | 0.04 |
| Extreme | 0.18 |

**Operational Insight:**  
Monitoring load itself can serve as an **early proxy for clinical deterioration**, even before outcomes occur.

---

### **3️⃣ Length of Stay & Mortality**

* Patients who died in hospital:  
  * Had a **higher mean hospital LOS, nearly 11 days**  
  * Had a **higher median hospital LOS, nearly 8.5 days**  
* Mortality is associated with **prolonged care**, not sudden deterioration.

**Operational Insight:**  
Early escalation or intervention may reduce prolonged, high-cost hospitalizations.

---

### **4️⃣ ICU & Mortality Relationship**

* All in-hospital deaths occurred **after ICU admission**.  
* ICU care appears to be a **necessary intervention** for the most severe cases.

**Operational Insight:**  
ICU utilization reflects severity rather than inefficiency, reinforcing its role in managing critical patients.

---

## **Data Visuals**

Only two executive plots are used:

1. **Monitoring Intensity vs Mortality**: validates early risk signals  
2. **Length of Stay vs Mortality**: highlights resource concentration

These plots are designed for **clinical leadership and product strategy discussions**.

---

## **Business Applications**

This analysis supports:

* Early-warning dashboards for clinicians  
* ICU triage prioritization  
* Staffing and monitoring allocation  
* Risk-aware clinical decision support systems  
* Hospital cost containment strategies

---

## **Tools & Skills Used**

* **Python** (Pandas, NumPy)  
* **Data aggregation & feature engineering**  
* **Clinical operations analytics**  
* **Matplotlib for visualizations**

---

## **Disclaimer**

This project uses **public, de-identified demo data** for educational and portfolio purposes only.  
No clinical decisions should be made based on this analysis.

---

## **Author**

**Vaishnavi Patil**  
Data Analyst | Healthcare & Clinical Analytics

