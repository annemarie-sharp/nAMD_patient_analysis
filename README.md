# Exploring neovascular Age-related Macular Degeneration (nAMD) Patient Characteristics (Moorfields Eye Hospital) 

## Table of Contents
- [Project Overview](#project-overview)
- [Data Source](#data-source)
- [Tools](#tools)
- [Data Preparation and Cleaning](#data-preparation-and-cleaning)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Data Analysis](#data-analysis)
- [Insights](#insights)


---

## Project Overview
This R-based data analysis project explores the characteristics of patients with neovascular Age-related Macular Degeneration (AMD). The analysis uses an anonymized dataset from Moorfields Eye Hospital containing patients who underwent intravitreal anti-VEGF therapy.

The objective is to uncover demographic patterns and clinical trends across three key areas: **gender distribution**, **age group representation**, and the **relationship between age and visual acuity**. By summarizing unique patient counts for demographic analysis and visualizing the distribution of visual acuity across different age groups, this project aims to provide insights into this specific patient population.

---

## Data Source
- **Source:** The `eyedata` R package  
- **Dataset:** `amd2`  
- **Description:** A dataset containing anonymized real-life human subjects data on eyes with treatment-naïve neovascular age-related macular degeneration (AMD), which underwent intravitreal anti-VEGF therapy with ranibizumab and/or aflibercept.

---

## Tools
- **Language:** R
- **Packages:**
  - `dplyr` — data manipulation, cleaning, and summarization
  - `ggplot2` — static, high-quality data visualizations
  - `eyedata` — source of the `amd2` dataset

---

## Data Preparation and Cleaning
The following steps were performed in R:

1. **Handling Missing Values:**  
   The two missing entries in the `visual_acuity` column, which resulted from data entry errors in the source records, were filtered out before visualization.

2. **Column Renaming:**  
   Columns were renamed for better readability (e.g., `age0` → `baseline_age`, `va` → `visual_acuity`).

3. **Data Summarization:**  
   To analyze demographics accurately, the data was processed to count each patient **only once**.

4. **Data Transformation:**  
   A new `age_group` column was created by binning `baseline_age` into 10-year intervals (e.g., `60–69`, `70–79`) to facilitate age-based analysis.

---

## Exploratory Data Analysis
Guiding questions for the EDA included:

1. What is the gender distribution of patients in the dataset?  
2. How are the patients distributed across different age groups?  
3. How does visual acuity, measured in **ETDRS** (Early Treatment Diabetic Retinopathy Study) letters, vary across these age groups?

---

## Data Analysis
The analysis was performed entirely within R. The **dplyr** package was used for all data wrangling tasks, including filtering, grouping, and summarizing the dataset to prepare it for visualization. Key steps involved isolating unique patients for demographic counts and categorizing patients into age groups.

Following data preparation, the **ggplot2** package was used to generate three plots that visually represent the findings related to patient gender, age, and visual acuity.

---

## Insights
Key insights drawn from the analysis:

- **Gender Distribution:**  
  Neovascular age-related macular degeneration (AMD) appears more prevalent in **female** patients than in male patients within this cohort.

- **Age Group Distribution:**  
  As expected for an age-related condition, the patient population is concentrated in the older age brackets. The visualization shows that the **80–89** age group contains the highest number of patients.

- **Visual Acuity and Age:**  
  The boxplot shows that visual acuity remains relatively stable in the age groups **60–69**, **70–79**, **80–89**, with only small shifts in the median values, but by **90–99** there is a clearer decline and greater variation, suggesting that advanced age is associated with lower visual acuity. The many outliers clustered at low visual-acuity values across all age groups indicate that severe vision impairment can occur at any age.

---
