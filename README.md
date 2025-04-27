# Team 2
# Critical Care Index (CCI) Dashboard

## Purpose

This dashboard provides a visual interface for monitoring and analyzing the condition of mock Intensive Care Unit (ICU) patients using a calculated Critical Care Index (CCI). It aims to offer insights into patient acuity trends and the underlying factors contributing to their condition over a 24-hour period.

## Core Functionalities

•⁠  ⁠*Patient Monitoring:* Allows users to select from a list of mock patients and view their specific data. Basic demographic information (Age, Gender, Length of Stay, Survival Status) for the selected patient is displayed.
•⁠  ⁠*CCI Visualization:* Presents the patient's Critical Care Index (CCI) score (ranging from 0-24) as it changes over the first 24 hours of monitoring. This is shown on an interactive chart.
•⁠  ⁠*Risk Stratification:* The CCI score is automatically categorized into risk levels (Low, Moderate, High, Severe). These levels are visually represented on the main chart using color-coded zones and reference lines, allowing for quick assessment of patient severity.
•⁠  ⁠*Detailed Clinical Parameter Views:* Offers dedicated charts showing the trends of key (mock) clinical parameters over the 24-hour period, such as:
    * Net Fluid Balance (using mock data)
    * Vasopressor/Inotrope Dose (using mock data)
    * Mechanical Ventilation Status (using mock data)
    * Lactate/Creatinine levels (using mock data)
•⁠  ⁠*Explainability (Shapley Analysis):* Provides insights into why the CCI score is at a certain level at a specific point in time. It uses a waterfall chart to break down the score, showing how different factors (like respiratory status, cardiovascular indicators, renal function, coagulation, demographics, and vital signs) contribute positively or negatively to the final CCI value.

## Key Concepts Explained

•⁠  ⁠*Critical Care Index (CCI):* This is a synthetic score calculated based on several clinical parameters representing different organ systems (Respiratory, Cardiovascular, Renal, Coagulation). A higher score indicates greater patient acuity or severity of illness. The calculation rules are embedded within the application using the ⁠ calculateCCI ⁠ logic based on metrics like P/F ratio, SpO2/FiO2, Mean Blood Pressure, Urine Output, and Platelets.
•⁠  ⁠*Shapley Values:* These values are used in the "Shapley Analysis" view to quantify the contribution of each input feature (e.g., respiratory score, age, heart rate) to the difference between the patient's actual CCI score and an average baseline score. This helps identify the primary drivers of the patient's condition at that moment.

## Dashboard Views

The dashboard offers different perspectives on the patient's data through selectable views:

1.  *Overview:* The primary view showing the 24-hour CCI trend chart with risk zones. Users can hover over points for quick info (via a custom tooltip) and click on a specific time point to analyze it further in the Shapley view.
2.  *Detailed View:* Focuses on the individual trajectories of the mock clinical parameters mentioned above, allowing for a more granular look at specific physiological systems over time.
3.  *Shapley Analysis:* Activated by clicking a point on the Overview chart. This view displays the waterfall chart detailing the contributions to the CCI score for that selected time point, along with a summary of component importance.

## Data Source

This dashboard currently operates using *mock data* generated internally by the ⁠ loadPatientData ⁠ function. This includes synthetic patient demographics, vital signs, calculated CCI scores, and corresponding Shapley values designed to simulate realistic ICU patient scenarios, including different trajectories based on simulated survival outcomes. In a real-world application, this data would be sourced from live hospital systems or clinical databases.
