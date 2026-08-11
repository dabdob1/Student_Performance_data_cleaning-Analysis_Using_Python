# 📊 Student Performance Analysis

A data analysis project exploring **student academic performance** using Python, Pandas, NumPy, and Matplotlib.

The goal of this project is to understand student performance, validate data quality, identify important patterns, compare student groups, and discover factors associated with higher or lower academic performance.

---

## 📌 Project Overview

This project analyzes the performance of **1,000 students** across three subjects:

* 🧮 Math
* 📖 Reading
* ✍️ Writing

The analysis investigates:

* Data quality and validation
* Missing values and duplicates
* Invalid score detection
* Statistical summaries
* Outlier analysis
* Performance bands
* Group comparisons
* Test preparation impact
* Lunch category differences
* Gender differences
* Race/ethnicity differences
* Parental education differences
* Correlation between subjects
* Multivariate analysis
* Key business-style questions adapted to education

---

## 📂 Dataset

**Dataset:** `StudentsPerformance.csv`

The original dataset contains:

* **1,000 students**
* **8 original columns**
* 3 numerical score columns
* 5 categorical columns

### Main Features

| Column                        | Description                                    |
| ----------------------------- | ---------------------------------------------- |
| `gender`                      | Student gender                                 |
| `race/ethnicity`              | Student race/ethnicity group                   |
| `parental level of education` | Parent's highest education level               |
| `lunch`                       | Lunch category                                 |
| `test preparation course`     | Whether the student completed test preparation |
| `math score`                  | Math score                                     |
| `reading score`               | Reading score                                  |
| `writing score`               | Writing score                                  |

---

## 🛠️ Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Jupyter Notebook / Google Colab

---

## 🔍 Data Quality Analysis

The project performs several validation checks before analyzing the data.

### Checks performed

* Dataset dimensions
* Column names
* Data types
* Missing values
* Duplicate rows
* Categorical consistency
* Leading/trailing whitespace
* Score range validation
* Outlier detection

### Data Quality Results

| Check             | Result |
| ----------------- | -----: |
| Students          |  1,000 |
| Original columns  |      8 |
| Missing values    |      0 |
| Duplicate rows    |      0 |
| Invalid scores    |      0 |
| Valid score range |  0–100 |

No student records were removed from the original dataset.

---

## 📈 Feature Engineering

Two analytical measures were created without modifying the original dataset:

### Average Score

```python
average_score = mean(math, reading, writing)
```

### Total Score

```python
total_score = math + reading + writing
```

### Pass-All Indicator

A student is considered to have passed all subjects when:

```text
Math >= 50
Reading >= 50
Writing >= 50
```

### Performance Bands

Students are classified into four groups:

| Average Score | Performance Band |
| ------------: | ---------------- |
|          < 50 | Below 50         |
|         50–69 | 50–69            |
|         70–84 | 70–84            |
|        85–100 | 85–100           |

---

## 📊 Exploratory Data Analysis

The project includes:

### Univariate Analysis

* Score distributions
* Histograms
* Box plots
* Performance bands
* Outlier identification

### Bivariate Analysis

Performance is compared across:

* Gender
* Race/ethnicity
* Parental education
* Lunch category
* Test preparation

### Multivariate Analysis

The project also investigates combinations such as:

* Lunch × Test Preparation
* Gender × Test Preparation

---

## 🔗 Correlation Analysis

Correlation analysis is used to understand relationships between:

* Math
* Reading
* Writing
* Average score

### Key Finding

Reading and writing scores have a **very strong relationship**.

Math is also strongly related to reading and writing, although the relationship between reading and writing is stronger.

> Correlation indicates association and does not prove causation.

---

# 💡 Key Insights

## 1. Overall Performance

The overall average score across the three subjects is:

**67.77**

Subject averages:

| Subject | Average |
| ------- | ------: |
| Reading |   69.17 |
| Writing |   68.05 |
| Math    |   66.09 |

📌 **Reading is the strongest subject, while Math has the lowest average.**

---

## 2. Pass Rate

**812 out of 1,000 students** scored at least 50 in all three subjects.

### Overall Pass-All Rate

**81.2%**

---

## 3. Test Preparation

Students who completed the test preparation course achieved:

**72.67 average score**

Students without preparation achieved:

**65.04 average score**

This represents an observed performance difference of approximately:

**+7.63 points**

📌 Students who completed test preparation performed better in this dataset.

⚠️ This is an association and does not prove that test preparation alone caused the improvement.

---

## 4. Lunch Category

Students with standard lunch achieved:

**70.84 average score**

Students with free/reduced lunch achieved:

**62.20 average score**

Difference:

**+8.64 points**

📌 The dataset shows a substantial performance difference between the two lunch categories.

⚠️ The dataset does not establish the reason or causality behind this difference.

---

## 5. Race/Ethnicity

The highest average performance was observed in:

**Group E — 72.75**

The lowest average performance was observed in:

**Group A — 62.99**

---

## 6. Parental Education

Highest average performance:

**Master's degree — 73.60**

Lowest average performance:

**High school — 63.10**

---

## 7. Gender

Female students:

**69.57 average**

Male students:

**65.84 average**

Difference:

**+3.73 points**

Female students had the higher overall average in this dataset.

---

## ⚠️ Important Analytical Limitations

This dataset does **not** contain a time variable.

Therefore, this project cannot determine:

* Whether performance is increasing over time
* Whether performance is decreasing over time
* When performance changed
* Whether a specific intervention caused improvement

The observed relationships should be interpreted as **associations, not causal relationships**.

---

## 🧹 Outlier Handling

Outliers were detected using the **IQR method**:

```text
IQR = Q3 - Q1

Lower Bound = Q1 - 1.5 × IQR

Upper Bound = Q3 + 1.5 × IQR
```

Some unusually low scores were identified.

However, these scores were still valid because they remained within the expected **0–100** range.

Therefore:

> Outliers were flagged for investigation rather than deleted.

---

## 📁 Project Structure

```text
Student-Performance-Analysis/
│
├── StudentsPerformance.csv
│
├── Student_Performance_Analysis.ipynb
│
├── README.md
│
└── images/
    ├── score_distribution.png
    ├── performance_bands.png
    ├── correlation_matrix.png
    └── group_comparison.png
```

---

## 🚀 How to Run

### 1. Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/student-performance-analysis.git
```

### 2. Navigate to the project

```bash
cd student-performance-analysis
```

### 3. Install dependencies

```bash
pip install pandas numpy matplotlib jupyter
```

### 4. Run Jupyter Notebook

```bash
jupyter notebook
```

Open:

```text
Student_Performance_Analysis.ipynb
```

---

## 📌 Future Improvements

For a more advanced version of this project, the dataset could include:

* Exam date
* Semester
* Academic year
* Multiple assessments per student
* Attendance
* Study hours
* Previous grades
* School information

This would allow deeper analysis of **student performance trends over time** and potentially support predictive modeling.

---

## 🎯 Conclusion

The analysis shows several meaningful differences in student performance.

The strongest observed patterns are associated with:

1. **Test preparation**
2. **Lunch category**
3. **Parental education**
4. **Race/ethnicity**
5. **Gender**

Students who completed test preparation and students in the standard-lunch category had higher average scores in this dataset.

However, these findings represent **observed associations rather than causal effects**.

The project demonstrates a complete beginner-to-intermediate data analysis workflow:

```text
Raw Data
   ↓
Data Validation
   ↓
Data Quality
   ↓
Statistical Analysis
   ↓
Feature Engineering
   ↓
EDA
   ↓
Outlier Analysis
   ↓
Correlation Analysis
   ↓
Group Comparison
   ↓
Insights & Conclusions
```

---

## 👨‍💻 Author

**David**

Data Analysis | Python | Pandas | Data Visualization

---

⭐ If you found this project useful, consider giving the repository a star!
