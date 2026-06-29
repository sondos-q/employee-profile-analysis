# Employee Data Analysis

Exploratory data analysis (EDA) on a sample employee dataset of 1,000 employees to ensure the workplace remains fair and efficient, covering demographics, compensation, tenure, and attrition.

## Dataset

**File:** `Employee Sample Data - A(1).xlsx`  
**Records:** 1,000 employees | **Features:** 14 columns

| Column | Type | Description |
|---|---|---|
| EEID | str | Unique employee ID |
| Full Name | str | Employee full name |
| Job Title | str | Role/position |
| Department | str | Department (IT, Finance, etc.) |
| Business Unit | str | Business unit (Manufacturing, R&D, etc.) |
| Gender | str | Gender |
| Ethnicity | str | Ethnicity |
| Age | float | Age in years |
| Hire Date | datetime | Date of hire |
| Annual Salary | float | Annual salary (USD) |
| Bonus % | float | Bonus percentage (0.0 – 0.4) |
| Country | str | Country of employment |
| City | str | City of employment |
| Exit Date | datetime | Date of exit (NaT if still employed) |

### Key Stats

| Metric | Value |
|---|---|
| Average Age | 44.4 years |
| Average Salary | $113,373 |
| Average Bonus | 8.9% |
| Still Employed | ~91.5% |

## Data Cleaning

- **No duplicates** found
- **Dropped** 2 rows with missing `Full Name`
- **Categorical / date / age nulls** filled with the column mode
- **Numerical nulls** (`Annual Salary`, `Bonus %`) filled with the column median
- **Engineered feature:** `Still Working` (bool) — `True` if `Exit Date` is null

## Key Findings

### 1. Salary, Bonus & Age (Figure 1 — Pairplot)
- Strong positive relationship between Annual Salary and Bonus.
- No meaningful relationship between Age and either Annual Salary or Bonus.
- Annual Salary distribution is right-skewed — most salaries fall below the mean.
- Bonus distribution shows that most employees receive no bonus (0%).

### 2. Age Distribution (Figure 2 — Histogram)
- Age range spans 25 to 65 years.
- Most frequent age group is 43–47, with approximately 120 employees.

### 3. Business Unit Distribution (Figure 3 — Count Plot)
- Manufacturing is the largest business unit by headcount.

### 4. Department & Salary by Department (Figures 4 & 5)
- IT is the largest department (~250 employees); Accounting is the smallest (~100 employees).
- Marketing has the highest average annual salary (~$130,000); IT has the lowest (~$100,000).

### 5. Gender & Salary by Gender (Figures 6 & 7)
- Gender distribution is nearly balanced: 51.9% female, 48.1% male.
- Average annual salary is equal across genders.

### 6. Country & Salary by Country (Figures 8 & 9)
- 64.2% of employees are based in the United States; Brazil has the smallest share at 13.9%.
- Average salary is consistent across all countries.

### 7. Ethnicity Distribution (Figure 10)
- Asian employees make up the largest ethnic group (~400 employees).
- Black employees make up the smallest group (~75 employees).

### 8. City Distribution (Figure 11)
- Employees are spread across 13 cities.
- Seattle has the highest headcount (~120); Manaus has the lowest (~40).

### 9. Employee Status (Figure 12)
- ~900 employees are currently active; ~100 have left the company (90% retention rate).

### 10. Zero-Bonus by Department (Figure 13)
- IT has the highest number of employees receiving a 0% bonus.
- Accounting has the lowest number of employees receiving a 0% bonus.

## Conclusion

- Average salaries are equal across genders, with an almost balanced workforce (51.9% female / 48.1% male).
- There is a strong positive relationship between Annual Salary and Bonus percentage.
- The Marketing department receives the highest average annual salary at ~$130,000.
- The IT department is the largest (~250 employees) yet has the lowest average salary (~$100,000) and the highest proportion of zero-bonus employees.
- The workforce is highly stable — 90% of employees (900 out of 1,000) remain active.

## Requirements

```
pandas
openpyxl
seaborn
matplotlib
numpy
```

Install with:

```bash
pip install pandas openpyxl seaborn matplotlib numpy
```

## Usage

```bash
python analysis.py
```

Make sure `Employee Sample Data - A(1).xlsx` is in the same directory as the script.
