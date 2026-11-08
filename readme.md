# 🚲 Cyclistic Bike-Share Data Analysis Case Study

![Data Science](https://img.shields.io/badge/Domain-Data%20Analytics%20%26%20ML-blue)
![Python](https://img.shields.io/badge/Python-3.8%2B-brightgreen)
![License](https://img.shields.io/badge/License-MIT-orange)

An end-to-end data analytics case study evaluating **10.3M+ historical ride records** from Cyclistic (a fictional bike-share program based in Chicago). This project follows the Google Data Analytics methodology (**Ask, Prepare, Process, Analyze, Share, Act**) to identify behavioral differences between annual members and casual riders and recommend data-driven marketing strategies to drive membership conversions.

---

## 📌 Table of Contents
- [Business Scenario](#-business-scenario)
- [Key Questions](#-key-questions)
- [Dataset Overview](#-dataset-overview)
- [Project Architecture & Directory Structure](#-project-architecture--directory-structure)
- [Methodology & Data Pipeline](#-methodology--data-pipeline)
- [Key Insights & Visualizations](#-key-insights--visualizations)
- [Business Recommendations](#-business-recommendations)
- [Tech Stack & Tools](#-tech-stack--tools)
- [How to Run](#-how-to-run)
- [License & Acknowledgments](#-license--acknowledgments)

---

## 🚴 Business Scenario

Cyclistic's finance team concluded that **annual members are significantly more profitable than casual riders** (single-ride and full-day pass users). 

Lily Moreno, Director of Marketing, aims to maximize future growth by converting existing casual riders into annual members rather than targeting all-new prospects. To achieve this, the marketing team needs clear insights into how casual riders and annual members use Cyclistic bikes differently.

---

## ❓ Key Questions

1. **How do annual members and casual riders use Cyclistic bikes differently?** *(Primary Focus)*
2. **Why would casual riders buy a Cyclistic annual membership?**
3. **How can Cyclistic use digital media to influence casual riders to become members?**

---

## 📊 Dataset Overview

* **Source:** Historical bike-share data provided by Motivate International Inc. under [this license](https://www.divvybikes.com/data-license-agreement).
* **Volume:** 10.3M+ trip records spanning 12 months.
* **Attributes:** `ride_id`, `rideable_type`, `started_at`, `ended_at`, `start_station_name`, `end_station_name`, `start_lat`, `start_lng`, `end_lat`, `end_lng`, `member_casual`.

---

## 📂 Project Architecture & Directory Structure

```bash
cyclistic-bikeshare-analysis/
│
├── data/
│   ├── raw/                 # Original 12-month raw CSV files (gitignored)
│   └── processed/           # Cleaned and engineered dataset
│
├── notebooks/
│   ├── 01_data_cleaning.ipynb      # Schema unification & null/outlier handling
│   ├── 02_feature_engineering.ipynb # Haversine distance, day of week, ride lengths
│   └── 03_eda_and_insights.ipynb    # Aggregations, statistical analysis & plots
│
├── outputs/
│   └── graphs/              # Exported high-resolution visual plots (.png)
│
├── cyclistic_case_study_report.md  # Detailed case study report (Deliverables 1-6)
├── requirements.txt         # Required Python packages
├── .gitignore               # Ignored raw data and cache folders
└── README.md                # Project overview and documentation
```

---

## 🛠️ Methodology & Data Pipeline

The analysis strictly adheres to the six-phase data analysis process:

1. **Ask:** Define the business problem, key stakeholders, and strategic objectives.
2. **Prepare:** Assess data credibility using the **ROCCC** framework (Reliable, Original, Comprehensive, Current, Cited) and verify licensing and privacy constraints.
3. **Process:** 
   * Unified 12 monthly dataframes into a consolidated structure.
   * Filtered negative durations, system maintenance records, and trips $> 24$ hours.
   * Engineered columns: `ride_length` (minutes), `day_of_week`, `start_hour`, `month`, and spatial distance (`haversine_distance`).
4. **Analyze:** Aggregate metrics (mean ride times, peak usage hours, weekly/seasonal distributions) categorized by `member_casual`.
5. **Share:** Design executive-ready visualizations emphasizing key user trends.
6. **Act:** Formulate data-backed recommendations for executive approval.

---

## 📈 Key Insights & Visualizations

| Dimension | Annual Members | Casual Riders |
| :--- | :--- | :--- |
| **Primary Motivation** | Daily Commuting / Functional Routine | Weekend Leisure / Recreation |
| **Average Ride Duration** | $\sim 12 - 15$ minutes | $\sim 28 - 35$ minutes |
| **Peak Days** | Weekdays (Tuesday – Thursday) | Weekends (Saturday – Sunday) |
| **Peak Hours** | 8:00 AM & 5:00 PM (Bimodal Commute) | 12:00 PM – 5:00 PM (Unimodal Afternoon) |
| **Seasonality** | Consistent year-round usage | Heavy spike in Summer (May – August) |

---

## 💡 Top Business Recommendations

1. **Seasonal "Summer Upgrade" Campaign:** Launch a targeted promotion from May through August offering casual riders a discount equal to their recent pass purchases when upgrading to an annual membership.
2. **Long-Ride / Weekend Membership Tiers:** Market annual membership features that offer extended time limits or weekend-specific benefits designed for leisure riders.
3. **Geofenced Digital Advertising:** Deploy in-app prompts and geofenced social media ads near high-volume casual stations (waterfronts, parks, tourist spots) during peak weekend afternoon hours.

---

## 💻 Tech Stack & Tools

* **Language:** Python 3.8+
* **Data Manipulation:** `pandas`, `numpy`
* **Data Visualization:** `matplotlib`, `seaborn`
* **Geospatial Processing:** Haversine formula calculation
* **Documentation:** Markdown

---

## 🚀 How to Run

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/cyclistic-bikeshare-analysis.git
cd cyclistic-bikeshare-analysis
```

### 2. Set Up Virtual Environment & Install Dependencies
```bash
python -m venv venv
source venv/bin/activate  # On Windows use: venv\Scripts\activate
pip install -r requirements.txt
```

### 3. Run Notebooks
Launch Jupyter Notebook to execute the data processing and analysis scripts:
```bash
jupyter notebook notebooks/
```

---

## 📜 License & Acknowledgments

* **Data License:** Data made available by Motivate International Inc. under its public [license agreement](https://www.divvybikes.com/data-license-agreement).
* **Project Framework:** Based on the **Google Data Analytics Professional Certificate** Capstone Project.