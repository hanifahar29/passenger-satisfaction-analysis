![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![PowerBI](https://img.shields.io/badge/Power_BI-F2C811?style=for-the-badge&logo=power-bi&logoColor=black)
![License](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)

# ✈️ Passenger Satisfaction: Root Cause & Strategic Investment Analysis
![PBIDesktop_y9TeLJM2YS](https://github.com/user-attachments/assets/42546f52-a7f8-4f88-b663-afc6c4741f41)

## 📌 Business Context
Current data shows that passenger satisfaction is only at **43.45%**. In a highly competitive aviation market, this low rating indicates a significant risk of customer churn and loss of brand equity. 

Management has a limited budget and cannot improve every service at once. This project was designed to solve two critical business questions:
1. **Identify the Friction:** Which specific service touchpoints are causing the biggest "Gap" in satisfaction?
2. **Maximize ROI:** Where should the company invest to see the fastest increase in satisfaction scores?

---

## 🛠️ Tech Stack & Workflow

### 🐍 Data Processing (Python)
Data preparation is crucial to ensure that extreme flight delays or inconsistent entries do not skew the statistical results.
* **Outlier Handling:** Capped extreme delay values to ensure accurate KPI metrics.
* **Missing Value Imputation:** Handled missing values in delay columns to validate "on-time" assumptions.
* **Feature Engineering:** Created Age and Distance groups to identify specific demographic pain points.
* **Statistical Validation:** Transformed satisfaction into a binary measure to calculate correlation ($p$-value) and identify primary drivers.

### 📊 Interactive Analysis (Power BI)
A dynamic dashboard was developed to visualize service failures and segment trends for stakeholders.
* **Gap Analysis:** Built a "Gap Score" measure to quantify the difference in experience between satisfied and dissatisfied passengers.
* **Target Segmentation:** Discovered that dissatisfaction is heavily concentrated in the **Economy Class** and **Personal Travel** segments.

---

## 📈 Dashboard Visualization Details
This section details the logic behind each visualization used to identify passenger satisfaction issues:

### 1. Overall Satisfaction Rate (Gauge Chart)

<img width="157" height="115" alt="PBIDesktop_qrtq6EEcn6" src="https://github.com/user-attachments/assets/6afc4aec-d1f6-4b2e-8c4f-b581528d0f86" />

* **Logic:** Displays the percentage of satisfied passengers compared to the total passenger population.
* **Insight:** Currently at **43.45%**, serving as the baseline to reach the 65% improvement target.

### 2. Gap Score by Service (Column Chart)

<img width="266" height="174" alt="PBIDesktop_C2MNbBD6Fs" src="https://github.com/user-attachments/assets/d37c4c3c-4f6d-4468-93a5-24f76f156a5f" />

* **Logic:** To identify the exact service failure points, I implemented a custom DAX logic to quantify the "Experience Gap." This measures the disparity in service ratings between satisfied and dissatisfied segments, allowing for a precise identification of service bottlenecks.
* **Why Use Gap Score?:**
  - **Identifying Service Failures:** It highlights the contrast between satisfied and dissatisfied experiences rather than just looking at averages.
  - **Prioritizing Investment:** Services with the highest Gap Score represent the "biggest pain points" where improvements will yield the highest impact.

```dax
Gap Score = 
VAR AvgSatisfied = CALCULATE(AVERAGE('Airlines_cleaned'[Score]), 'Airlines_cleaned'[Satisfaction_Biner] = 1)
VAR AvgDissatisfied = CALCULATE(AVERAGE('Airlines_cleaned'[Score]), 'Airlines_cleaned'[Satisfaction_Biner] = 0)
RETURN AvgSatisfied - AvgDissatisfied
```

* **Key Finding:** **Online Boarding** (Gap: **1.37**) and **In-flight Entertainment** (Gap: **1.07**) show the highest gaps, marking them as the primary service failure points.
  
### 3. Satisfaction by Flight Class & Travel Type (Bar & Pie Charts)

<img width="210" height="243" alt="PBIDesktop_ZQ3nN23WB3" src="https://github.com/user-attachments/assets/1c3efcea-2e83-4bbd-81e8-28bc775e3006" />

* **Logic:** Segments data by class (Business, Economy, Economy Plus) and purpose of travel (Personal vs. Business).
* **Insight:** The highest dissatisfaction is found among **Economy Class** passengers and those on **Personal Travel**.

### 4. Satisfaction by Customer Type & Distance Group (Bar & Donut Charts)

<img width="404" height="123" alt="PBIDesktop_1ssVr9OXwq" src="https://github.com/user-attachments/assets/911bc851-57d1-44b2-bc82-48ec54ab2a8f" />

* **Logic:** Compares satisfaction levels between **First-time** vs. **Returning** customers and flight distances.
* **Insight:** Retention efforts should be directed at **Returning Customers**, as they represent the largest user base but show significant dissatisfaction on **Long Haul** routes.

---

## 🔍 Key Findings & Statistical Validation
The analysis confirms that technical and digital service quality is the central issue, rather than operational delays.

<img width="363" height="307" alt="chrome_q1Gsx4KFnC" src="https://github.com/user-attachments/assets/1745db82-efd6-4c73-a7ed-ea2fa95c6fa4" />

### Statistical Validation of Root Causes:
* **Primary Driver Confirmation:** Correlation Analysis confirms our priority: **Online Boarding** is the strongest driver of satisfaction ($p=0.50$).
* **Strategic ROI Focus:** Fixing the top two correlated services, **Online Boarding** ($p=0.50$) and **In-flight Entertainment** ($p=0.40$), guarantees the greatest return on investment (ROI) in satisfaction scores.
* **Operational Impact:** Departure and Arrival time convenience showed minimal to negative correlation ($-0.05$), validating that delays are not the primary cause of dissatisfaction compared to service quality.

---

## 🚀 ACT - Prioritized Roadmap
Based on the data, I proposed a three-pillar investment strategy:

1. **Digital & Stability Investment:** Immediately launch a project to audit and upgrade Online Boarding server capacity and user flow.
2. **Physical Comfort & Retention:** Allocate budget for a targeted upgrade of In-flight Entertainment (IFE) content and improve Seat Comfort specifically for the Economy Class.
3. **Proactive Operational Improvement:** Implement a focused operational review to reduce the volatility (variance) of Arrival/Departure Delays.

---

## 📂 Dataset Source
The dataset used in this project is sourced from:
* **Kaggle:** [Airline Passenger Satisfaction](https://www.kaggle.com/datasets/teejmahal20/airline-passenger-satisfaction)

---

## ✅ Final Conclusion
This project demonstrates how data-driven prioritization can turn a low-satisfaction scenario into a strategic roadmap. By focusing on Online Boarding and In-flight Entertainment, the airline can bridge the satisfaction gap efficiently and move toward the 65% industry benchmark.

---

## 📬 Contact & Collaboration

I am always open to discussing data analytics, collaboration opportunities, or any feedback regarding this project. Feel free to reach out!

* **LinkedIn:** [Hanifah Arrasyidah](https://linkedin.com/in/hanifaharrasyidah)
* **GitHub:** [hanifahar29](https://github.com/hanifahar29)
  
> **Note:** For technical feedback or bug reports, please feel free to open an **Issue** or submit a **Pull Request** in this repository.

---
