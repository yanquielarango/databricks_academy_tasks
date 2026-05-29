
# 🧱 LEGO Sets Analysis

![PySpark](https://img.shields.io/badge/PySpark-E25A1C?style=for-the-badge&logo=apachespark&logoColor=white) ![Databricks](https://img.shields.io/badge/Databricks-FF3621?style=for-the-badge&logo=databricks&logoColor=white) ![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white) ![Delta Lake](https://img.shields.io/badge/Delta%20Lake-003366?style=for-the-badge&logo=delta&logoColor=white)

An exploratory analysis of the LEGO Sets dataset using PySpark on Databricks. I chose this dataset because it has a good mix of numeric and categorical columns, a fair amount of missing data to work with, and enough rows to make Spark worthwhile.

---

## 📦 Dataset

**LEGO Sets · Maven Analytics**  
A catalogue of LEGO sets from 1970 to the present — themes, piece counts, minifigures, retail prices, and more.

| | |
|---|---|
| Rows | 18,457 |
| Columns | 14 |
| Source | [Maven Analytics](https://mavenanalytics.io) |

---

## 🔍 What I did
1. Loaded the CSV from a Unity Catalog Volume and explored the schema and missing values
2. Filled nulls in `themeGroup` with `"Unknown"` and `agerange_min` with the median — dropping rows with 60%+ missing data made no sense
3. Added two derived columns:
   - `price_per_piece` — cost efficiency metric per set
   - `age_range` — categorizes sets by minimum age into buckets (1 to 4, 5 to 9, 10 to 17, Over 18)
4. Filtered to sets from 2000 onwards with a known piece count
5. Ran a SQL query grouped by year to compare total sets, average pieces, average price, and total minifigures
6. Saved the result as a Delta table — `lego_sets_by_year`

---

## 📁 Repo structure

```
databricks_academy_tasks/
    ├── LEGO_set/
    │   └── lego_sets.csv
    ├── taks/
    │   ├── tasks.dbc        # DBC archive — includes all cell outputs
    │   └── tasks.ipynb      # notebook source — importable in Databricks
    └── README.md
```

---

## 👤 Author

**Yanquiel Arango Gomez** — [GitHub](https://github.com/yanquielarango) · [Portfolio](https://www.datascienceportfol.io/yanquielarango)
