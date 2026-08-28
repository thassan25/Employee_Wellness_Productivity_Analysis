# Employee_Wellness_Productivity_Analysis
A Python-based data analysis project that explores employee demographics and health metrics using two structured datasets. The project covers data cleaning, statistical analysis, dataset merging, and data visualization.

---

## Skills & Tools

- **Programming Language:** Python
- **Libraries:** pandas, NumPy, Matplotlib
- **Environment:** Google Colab / Jupyter Notebook
- **Techniques:** Data cleaning, data merging, exploratory data analysis (EDA), descriptive statistics, correlation analysis, data visualization

---

## Repository Structure

```
📦 repository/
├── 📁 input/
│   ├── Employee_Details.csv          # Employee demographic and login data
│   └── Employee_Health.csv           # Employee health and productivity data
├── Tarmin_python_project.py          # Python script version of the analysis
├── Tarmin_python_project.ipynb       # Jupyter/Google Colab notebook version
├── Employee_Wellness_Productivity_Analysis_Insights        # Written summary of key findings and business insights
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

The analysis combines two source datasets — employee demographic details and employee health metrics — to examine how factors such as work hours, sleep, physical activity, and smoking status relate to employee stress and productivity. Departmental and demographic breakdowns are also produced to provide a workforce-level view.

**Key questions addressed:**
- What is the composition of the workforce by department and gender?
- How do stress and productivity levels vary across departments?
- Do lifestyle and work-habit factors (sleep, activity, work hours, smoking) meaningfully influence stress or productivity?
- Where are the data quality issues, and how were they addressed?

---

## Data Analysis Process

- **Data Import**
  - Loaded both CSV files (`Employee_Details.csv`, `Employee_Health.csv`) into pandas DataFrames.

- **Data Cleaning**
  - Removed duplicate records from both datasets.
  - Standardized the `Name` column by stripping special characters.
  - Corrected inconsistent category labels (e.g. gender entries such as "Mle" and "Fmale").
  - Standardized department names to a consistent case and labeled missing departments as "Unknown Department" rather than leaving them blank.
  - Split the combined `LastLogin` field into separate date and time columns.
  - Recoded `SmokingStatus` into a binary numeric format (1 = Smoker, 0 = Non-Smoker) to support quantitative analysis.

- **Data Integration**
  - Merged the employee and health datasets on `EmployeeID` using both inner and outer joins to preserve analytical flexibility.

- **Descriptive Statistics**
  - Calculated mean age and mean stress level across the workforce.
  - Calculated median work hours, minimum sleep hours, and maximum step count.

- **Grouped Analysis**
  - Aggregated data by department to compare mean age, productivity score, and employee headcount.
  - Aggregated data by gender to compare employee headcount and average stress level.

- **Correlation Analysis**
  - Evaluated the statistical relationship between work hours and productivity score.
  - Evaluated the statistical relationship between sleep, activity level, and smoking status against stress and productivity.

- **Data Visualization**
  - Built a horizontal bar chart of employee distribution across departments.
  - Built a bar chart of employee count by gender.
  - Built a bar chart of average stress level by gender.
  - Built a scatter plot of work hours versus productivity score, with correlation coefficient.
  - Built a line chart of employee last login activity trend.

---

## Business Impact

This analysis provides organizational stakeholders with a data-driven view of workforce composition and wellbeing that can inform HR strategy and employee wellness programs. Specifically, the findings:

- **Support workforce planning** by quantifying headcount and demographic balance across departments.
- **Challenge assumptions about productivity drivers** — the analysis found no meaningful correlation between common lifestyle factors (sleep, activity, smoking, work hours) and either stress or productivity, indicating that initiatives targeting these factors alone are unlikely to move productivity outcomes.
- **Identify wellbeing risk areas**, such as employees reporting critically low sleep hours, that merit further investigation independent of their productivity impact.
- **Establish a reusable data pipeline** for future workforce analytics, with cleaning and merging logic that can be applied to updated datasets on an ongoing basis.

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



