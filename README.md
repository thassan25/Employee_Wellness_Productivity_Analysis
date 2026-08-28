# Employee_Wellness_Productivity_Analysis
A Python-based data analysis project that explores employee demographics and health metrics using two structured datasets. The project covers data cleaning, statistical analysis, dataset merging, and data visualization.

---

## Repository Structure

```
📦 repository/
├── 📁 input/
│   ├── Employee_Details.csv          # Employee demographic and login data
│   └── Employee_Health.csv           # Employee health and productivity data
├── Tarmin_python_project.py          # Python script version of the analysis
├── Tarmin_python_project.ipynb       # Jupyter/Google Colab notebook version
├── Employee_Wellness_Productivity_Analysis_Insights        # Insight file
└── README.md                         # Project documentation
```

---

## Input Files

### `Employee_Details.csv`
Contains personal and employment information for each employee.

| Column | Description |
|---|---|
| `EmployeeID` | Unique identifier for each employee |
| `Name` | Employee full name |
| `Age` | Employee age |
| `Gender` | Employee gender |
| `Department` | Department the employee belongs to |
| `DateOfJoining` | Date the employee joined the company |
| `LastLogin` | Timestamp of the employee's last system login |

### `Employee_Health.csv`
Contains health and productivity metrics for each employee.

| Column | Description |
|---|---|
| `EmployeeID` | Unique identifier (matches `Employee_Details.csv`) |
| `Name` | Employee full name |
| `Gender` | Employee gender |
| `Department` | Department the employee belongs to |
| `WorkHours` | Average daily work hours |
| `StressLevel` | Self-reported stress level (numeric scale) |
| `SleepHours` | Average daily sleep hours |
| `ProductivityScore` | Productivity score (numeric) |
| `StepCount` | Daily step count |
| `HeartRate` | Heart rate measurement |
| `SmokingStatus` | Smoking status (`Smoker` / `Non-Smoker`) |
| `Comments` | Free-text comments |

---

## Project Overview

The analysis is broken into five questions:

### Question 1 — Data Loading
- Mounts Google Drive and loads both CSV files (`Employee_Details.csv` and `Employee_Health.csv`) into pandas DataFrames.

### Question 2 — Data Cleaning
Applies the following transformations to both datasets:

| Step | Transformation |
|---|---|
| 2a | Remove duplicate rows |
| 2b | Strip special characters (`/`, `1–9`, `.`, `_`) from `Name` column |
| 2c | Encode `SmokingStatus` as binary (`Smoker` → `1`, `Non-Smoker` → `0`) |
| 2d | Split `LastLogin` into separate `LastLogin_Date` and `LastLogin_Time` columns |
| 2e | Standardise `Department` values to uppercase |
| 2f | Fill missing `Department` values with `"UNKNOWN DEPARTMENT"` |

### Question 3 — Statistical Analysis
Calculates the following descriptive statistics using NumPy:

| Step | Metric |
|---|---|
| 3a | Average employee age |
| 3b | Average stress level |
| 3c | Median work hours |
| 3d | Minimum sleep hours |
| 3e | Maximum step count |

### Question 4 — Dataset Merging & Aggregation
- **4a** — Outer merge of both datasets on `EmployeeID`
- **4b** — Inner merge of both datasets on `EmployeeID`
- **4c** — Mean age grouped by department
- **4d** — Mean productivity score grouped by department
- **4e** — Employees sorted by productivity score (descending)

### Question 5 — Data Visualisation
Generates five Matplotlib charts:

| Step | Chart |
|---|---|
| 5a | Horizontal bar chart — Employee count by department |
| 5b | Bar chart — Employee count by gender (with gender data correction) |
| 5c | Bar chart — Average stress level by gender |
| 5d | Scatter plot — Productivity score vs. work hours (with correlation coefficient) |
| 5e | Line chart — Employee last login activity trend |

---

## Dependencies

| Library | Purpose |
|---|---|
| `pandas` | Data loading, cleaning, and manipulation |
| `numpy` | Statistical calculations |
| `matplotlib` | Data visualisation |
| `google.colab` | Google Drive mounting (Colab environment only) |
| `os` | File path handling |

Install the required libraries (if running locally):

```bash
pip install pandas numpy matplotlib
```

> **Note:** The `google.colab` import is only required when running in Google Colab. If running the `.py` script locally, replace the Drive mounting and file path logic with local file paths.

---

## How to Run

### Option 1 — Google Colab (Recommended)
1. Upload `Tarmin_python_project.ipynb` to [Google Colab](https://colab.research.google.com/).
2. Place the input CSV files in your Google Drive under the path:  
   `MyDrive/Python classes/Python project/`
3. Run all cells in order.

### Option 2 — Local Environment
1. Clone the repository.
2. Install dependencies using the command above.
3. Update the file paths in the script to point to your local input folder.
4. Run the script:
   ```bash
   python Tarmin_python_project.py
   ```

---

## Author

**Tarmin**  
Aspiring Data Analyst with hands-on experience in Excel, SQL, Python, PowerBI, Tableau and AI/ML. This repository showcases real-world projects built to solve practical data problems.

---

## Contact

**LinkedIn:** [www.linkedin.com/in/tarmin-hassan-099914a1]
**Email:** [tarminhassan@yahoo.com]
**GitHub:** [github.com/thassan25]



