# 🍽️ End-to-End Restaurant Data Analysis | Cognifyz Internship

![Python](https://img.shields.io/badge/Python-3.10-blue?style=flat&logo=python)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?style=flat&logo=pandas)
![Seaborn](https://img.shields.io/badge/Seaborn-Visualization-4C72B0?style=flat)
![Folium](https://img.shields.io/badge/Folium-Geospatial-77B829?style=flat)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=flat)

---

## 📌 About This Project

**End-to-End Restaurant Data Analysis** is my complete internship project at **Cognifyz Technologies**, where I was tasked with analyzing a large restaurant dataset across **2 Levels** and **6 Tasks** — covering the full data science pipeline from raw data exploration to feature engineering.

All analysis was performed on **Google Colab** using Python.

---

## 🏢 Internship Details

| Detail | Info |
|--------|------|
| **Company** | Cognifyz Technologies |
| **Role** | Data Science Intern |
| **Project** | End-to-End Restaurant Data Analysis |
| **Tools** | Python, Google Colab |
| **Total Tasks** | 6 (3 per Level) |
| **Status** | ✅ Completed |

---

## 📂 Repository Structure

```
end-to-end-restaurant-data-analysis/
│
├── notebooks/
│   ├── Level1_Task1_Data_Exploration_Preprocessing.ipynb
│   ├── Level1_Task2_Descriptive_Analysis.ipynb
│   ├── Level1_Task3_Geospatial_Analysis.ipynb
│   ├── Level2_Task1_Table_Booking_Online_Delivery.ipynb
│   ├── Level2_Task2_Price_Range_Analysis.ipynb
│   └── Level2_Task3_Feature_Engineering.ipynb
│
├── images/
│   ├── rating_distribution.png
│   ├── rating_distribution_rated_only.png
│   ├── geospatial_heatmap.png
│   ├── top_cities_cuisines.png
│   ├── price_vs_rating.png
│   ├── rating_color_chart.png
│   ├── online_delivery_price_range.png
│   └── cuisine_count.png
│
├── data/
│   └── dataset.csv
│
└── README.md
```

---

## 📊 Level 1

### ✅ Task 1 — Data Exploration & Preprocessing

**Objective:** Understand the raw dataset structure, identify quality issues, and clean the data for analysis.

**What I did:**
- Explored dataset shape, data types, and column information
- Identified and handled missing values
- Removed duplicates and irrelevant entries
- Standardized data types across columns
- Prepared a clean dataset ready for analysis

**Dataset Overview After Preprocessing:**

| Property | Detail |
|----------|--------|
| Total Records | 9,542 |
| Total Columns | 20 |
| Numerical Columns | 8 (int) + 3 (float) |
| Categorical Columns | 9 (object) |
| Missing Values | 0 (after cleaning) |

---

### ✅ Task 2 — Descriptive Analysis

**Objective:** Understand the dataset through statistical measures and categorical distributions.

**What I did:**
- Calculated mean, median, standard deviation, and skewness for all numerical columns
- Explored distribution of Country Code, City, and Cuisines
- Identified top cities and cuisines by restaurant count

**Statistical Summary:**

| Column | Mean | Median | Std Dev | Skewness |
|--------|------|--------|---------|----------|
| Average Cost for Two | 1,200 | 400 | 16,128 | 35.46 |
| Price Range | 1.80 | 2.0 | 0.91 | 0.89 |
| Aggregate Rating | 2.67 | 3.2 | 1.52 | -0.95 |
| Votes | 156.77 | 31.0 | 430.20 | 8.81 |

**Key Findings:**
- 🔍 Discovered **2,148 restaurants (22.5%)** had rating 0.0 — these are **"Not Rated"** not poor quality. After removing them, true average rating = **3.44**
- 💰 `Average Cost for Two` is extremely right-skewed (35.46) — **median (400) is far more reliable than mean (1,200)**
- 🏙️ **New Delhi dominates** with ~5,500 restaurants — top 4 cities are all Delhi NCR
- 🍛 **North Indian (~4,000)** and **Chinese (~2,700)** are the most popular cuisines

---

### ✅ Task 3 — Geospatial Analysis

**Objective:** Visualize restaurant locations and analyze geographic patterns using latitude & longitude.

**What I did:**
- Built 3 interactive maps using **Folium** — dot map, density heatmap, rating-colored map
- Analyzed restaurant distribution across countries and cities
- Investigated correlation between geographic location and rating

**Key Findings:**
- 🌍 **~90% of restaurants are from India (Country Code 1)** — major geographic bias
- 📍 Delhi NCR appears as the dominant hotspot across all maps
- 🏆 **Countries with fewer restaurants rate higher** — volume vs quality tradeoff
- 🇵🇭 **Philippine cities** dominate the highest-rated cities list (Inner City ~4.9, Quezon City ~4.8)
- 📉 Weak correlation between coordinates and rating (Latitude: -0.18, Longitude: -0.29)

**Interactive Maps Created:**

| Map | Description |
|-----|-------------|
| `restaurant_map.html` | All restaurant locations as interactive dots |
| `heatmap.html` | Density heatmap showing geographic concentration |
| `rated_map.html` | Color-coded by rating — green=highly rated, red=poorly rated |

---

## 📈 Level 2

### ✅ Task 1 — Table Booking & Online Delivery Analysis

**Objective:** Analyze adoption of table booking and online delivery features and their impact on ratings.

**What I did:**
- Calculated percentage of restaurants offering table booking and online delivery
- Compared average ratings with and without each feature
- Analyzed online delivery availability across all price ranges

**Key Findings:**
- 📋 Only **12.1%** of restaurants offer table booking — a premium/formal dining feature
- 🛵 **25.7%** offer online delivery — moderate adoption
- ⭐ Restaurants **with table booking rate higher (3.59 vs 3.41)** — signals quality establishment
- ❗ Restaurants **with delivery rate slightly lower (3.38 vs 3.47)** — delivery skews toward budget segment
- 🏆 **Price Range 2 (mid-range) leads online delivery at ~41%** — budget and premium both lag

---

### ✅ Task 2 — Price Range Analysis

**Objective:** Analyze price distribution, its relationship with ratings, and rating color mapping.

**What I did:**
- Determined the most common price range across all restaurants
- Calculated average rating per price range
- Identified which rating color represents the highest average rating

**Key Findings:**
- 💰 **Price Range 1 (Budget) is most common** — 4,438 restaurants (46.5%)
- 📈 **Price positively correlates with rating** — consistent staircase pattern:

| Price Range | Restaurants | Avg Rating |
|-------------|-------------|------------|
| 1 — Budget | 4,438 | 3.24 |
| 2 — Mid | 3,113 | 3.38 |
| 3 — Upper-Mid | 1,405 | 3.78 |
| 4 — Premium | 586 | 3.89 |

- 🟢 **Dark Green = Highest rated color** with average rating of **4.66**
- 🎨 Color scale: Dark Green (4.66) → Green (4.17) → Yellow (3.68) → Orange (3.05) → Red (2.30)

---

### ✅ Task 3 — Feature Engineering

**Objective:** Create new meaningful features from existing columns to enrich the dataset for future modeling.

**What I did:**
- Extracted text length features from restaurant name, address, and locality columns
- Applied ordinal encoding to Rating Text and Rating Color
- Created a Cuisine Count feature per restaurant
- Verified and confirmed existing binary features (Has Table Booking, Has Online Delivery)

**New Features Created:**

| Feature | Type | Description |
|---------|------|-------------|
| `Restaurant Name Length` | Numerical | Character count of restaurant name |
| `Address Length` | Numerical | Character count of full address |
| `Locality Length` | Numerical | Character count of locality |
| `Rating Text Encoded` | Ordinal (0–5) | Not rated=0 → Excellent=5 |
| `Rating Color Encoded` | Ordinal (0–5) | White=0 → Dark Green=5 |
| `Cuisine Count` | Numerical | Number of cuisines per restaurant |

**Key Findings:**
- 📝 Restaurant names peak at **10–15 characters** — short and memorable
- 🍽️ Most restaurants offer **1–2 cuisines (~72%)** — specialists dominate
- 🔢 Dataset enriched from **20 → 26 columns** after feature engineering

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|------|---------|
| **Python 3** | Core programming language |
| **Pandas** | Data manipulation & analysis |
| **NumPy** | Numerical computations |
| **Matplotlib** | Static visualizations |
| **Seaborn** | Statistical visualizations |
| **Folium** | Interactive geospatial maps |
| **Google Colab** | Cloud notebook environment |

---

## 💡 Key Takeaways

> **1.** Always investigate anomalies — 22.5% unrated restaurants were silently distorting all rating statistics

> **2.** Dataset bias matters — 90% India-centric data means conclusions can't be generalized globally

> **3.** Price signals quality — premium restaurants consistently rate 0.65 points above budget ones

> **4.** Feature engineering adds depth — 6 new features created from existing columns with zero new data

> **5.** Geography weakly influences ratings — cultural rating behavior matters more than coordinates

---

## 🤝 Acknowledgement

Thank you to **Cognifyz Technologies** for this internship opportunity and the structured task framework that guided this end-to-end restaurant data analysis project.

---

## 📬 Connect with Me

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0077B5?style=flat&logo=linkedin)](https://www.linkedin.com/in/praveen-kumar-chanapathi-927881354/?lipi=urn%3Ali%3Apage%3Ad_flagship3_profile_view_base_contact_details%3BbqHfmWpFRXKCXtlWbdQfjA%3D%3D)
[![GitHub](https://img.shields.io/badge/GitHub-Follow-181717?style=flat&logo=github)](https://github.com/praveenchanapathi09-cmyk)

---

*© 2024 | End-to-End Restaurant Data Analysis | Cognifyz Technologies Internship*
