# SaaS Customer Data Cleaning & Analysis 📊

A beginner-friendly **Python data cleaning and analysis project** built around SaaS customer subscription data.

This project was created as part of a Python/Data Science assignment and demonstrates how raw customer data can be **displayed, validated, standardized, cleaned, analyzed, and exported** using Python, Object-Oriented Programming (OOP), and Pandas.

---

## 🎯 Project Objective

The main objective of this project is to practice a basic data-processing workflow using a small SaaS customer dataset.

The project covers:

- Displaying customer records in a readable format
- Adding new customer records dynamically
- Validating and standardizing customer information
- Creating a reusable `Customer` class
- Standardizing different date formats
- Handling missing and invalid values
- Converting numeric fields into appropriate data types
- Removing duplicate customer records
- Identifying customers with low usage
- Finding unique SaaS subscription plans
- Saving plan-frequency results to a text file
- Using Pandas to read and analyze CSV data

---

## 📁 Dataset

The project uses SaaS customer subscription data containing the following fields:

| Column | Description |
|---|---|
| `customer_id` | Unique customer identifier |
| `name` | Customer name |
| `signup_date` | Customer signup date |
| `plan` | SaaS subscription plan |
| `monthly_fee` | Monthly subscription fee |
| `usage_hours` | Customer usage hours |

The sample data contains subscription plans such as **Basic, Pro, and Enterprise**.

The dataset intentionally contains data-quality issues such as:

- Different date formats
- Missing customer names
- Empty plan values
- Invalid monthly fee values such as `"forty-nine"`
- Missing/`NULL` usage-hour values
- Duplicate customer names

This makes the dataset useful for practicing real-world data-cleaning concepts.

---

## 🛠️ Technologies Used

### Programming Language

- Python

### Libraries / Modules

- `datetime`
- `pandas`

### Python Concepts

- Dictionaries
- Lists
- Loops
- Conditional statements
- Functions
- Sets
- Exception handling
- Type conversion
- String manipulation
- Object-Oriented Programming
- Classes and methods
- File handling

---

## 🔄 Project Workflow

```text
Raw SaaS Customer Data
        ↓
Display Customer Records
        ↓
Add New Customer Records
        ↓
Validate Input
        ↓
Standardize Date Formats
        ↓
Handle Missing & Invalid Values
        ↓
Convert Numeric Data Types
        ↓
Remove Duplicate Records
        ↓
Identify Low-Usage Customers
        ↓
Find Unique Subscription Plans
        ↓
Analyze Plan Occurrence
        ↓
Save Summary to Text File
```

---

## 📌 Tasks Implemented

### Task 1 – Display the Dataset

Customer records are displayed in a readable format using a `for` loop.

The output includes:

- Customer ID
- Name
- Signup date
- Plan
- Monthly fee
- Usage hours

### Task 2 – Add New Customer Records

The project accepts customer details dynamically through user input.

The input process includes:

- Customer name
- Signup date
- Subscription plan
- Monthly fee
- Usage hours

The customer ID is generated using the maximum existing customer ID plus one.

Multiple date formats are accepted and converted into the standard:

```text
YYYY-MM-DD
```

### Task 3 – Create SaaS Customer Class

An OOP-based `Customer` class is created to represent customer information.

The class contains:

- Customer attributes
- A `validate_data()` method
- A `display_customer()` method

The validation logic includes plan formatting, name handling, monthly-fee conversion, and usage-hour validation.

### Task 4 – Data Cleaning Pipeline

A reusable cleaning workflow is created using a `Customer` class.

The pipeline includes:

#### Date standardization

Different formats such as:

```text
2023-01-10
2023/02/15
03-01-2023
20230520
```

are converted to:

```text
YYYY-MM-DD
```

#### Missing-value handling

Examples include:

- Missing names → `Unknown Customer`
- Missing usage hours → `0`
- Invalid usage values → `0`
- Invalid monthly fee values → `None`

#### Duplicate removal

Duplicate customer names are detected using a Python `set` and duplicate records are removed.

### Task 5 – Summary Statistics and Insights

A section is included for summary statistics and insights. The notebook currently contains the structure for this task, but the implementation is not fully completed.

This section can be extended with Pandas-based statistics such as:

- Average monthly fee
- Average usage hours
- Number of customers by plan
- Minimum and maximum usage
- Monthly-fee statistics

### Task 6 – Identify Low-Usage Customers

Customers with usage below **50 hours** are identified.

This can help demonstrate how customer usage can be used to identify customers who may require additional engagement or support.

### Task 7 – Unique Plan Types

The project identifies unique subscription plans using Python sets and sorts them alphabetically.

Empty plan values are handled before generating the unique plan list.

### Task 8 – Save Cleaned Data to File

Pandas is used to read the customer CSV file and analyze the `plan` column.

Missing/empty plans are replaced with `"Unknown"` and plan frequencies are calculated using:

```python
value_counts()
```

The resulting plan summary is saved to:

```text
plan_summary.txt
```

---

## 📊 Dataset Example

The source dataset contains records similar to:

```text
customer_id | name          | signup_date | plan       | monthly_fee | usage_hours
------------|---------------|-------------|------------|-------------|------------
101         | Rahul Sharma  | 2023-01-10  | Pro        | 49.99       | 120
102         | Meena Nair    | 2023/02/15  | Basic      | 19.99       | 45
103         | Unknown       | 03-01-2023  | Pro        | invalid     | 88
104         | A. Kumar      | 15-04-2023  | Enterprise | 99.99       | NULL
```

The dataset is intentionally imperfect so that data-cleaning techniques can be practiced.

---

## 📂 Project Structure

```text
saas-customer-data-analysis/
│
├── Assignment2_Aug19_Srinithi_Kanniyappan_Saas.ipynb
├── customer_data.csv
├── plan_summary.txt
└── README.md
```

---

## ▶️ How to Run

### Option 1 – Google Colab

1. Open the `.ipynb` file in Google Colab.
2. Upload `customer_data.csv`.
3. Run the notebook cells from top to bottom.
4. Provide input when prompted for new customer records.
5. Review the cleaning and analysis outputs.
6. Check the generated `plan_summary.txt` file.

### Option 2 – Jupyter Notebook

Install the required library:

```bash
pip install pandas
```

Then open:

```text
Assignment2_Aug19_Srinithi_Kanniyappan_Saas.ipynb
```

and execute the cells sequentially.

> **Note:** The notebook contains some assignment cells that depend on interactive input and file paths. Update the CSV path if you are running the notebook outside Google Colab.

---

## 💡 Data Science Skills Demonstrated

Although this is a beginner-level project, it introduces several important skills used in data science:

### Data Cleaning

- Missing-value handling
- Invalid-value handling
- Date standardization
- Duplicate removal
- Data-type conversion

### Data Transformation

- String normalization
- Numeric conversion
- Categorization of missing values
- Creating cleaned records

### Data Analysis

- Filtering customers
- Identifying low-usage customers
- Finding unique categories
- Counting plan occurrences

### Programming

- Functions
- Loops
- Exception handling
- OOP
- File handling
- Pandas

---

## 🚀 Future Improvements

To develop this into a stronger Data Science portfolio project, the following improvements could be added:

- Perform complete Exploratory Data Analysis (EDA)
- Use Pandas DataFrames throughout the cleaning pipeline
- Create visualizations using Matplotlib and Seaborn
- Analyze customer usage by subscription plan
- Calculate customer lifetime value
- Identify high-value and low-engagement customers
- Analyze monthly subscription revenue
- Detect potential customer churn
- Build a churn prediction model
- Create a customer segmentation model
- Build an interactive dashboard using Power BI or Streamlit
- Add automated data-quality checks
- Add unit tests for the cleaning functions

---

## 🧠 What I Learned

Through this project, I practiced:

- Working with structured customer data
- Understanding common data-quality problems
- Cleaning and standardizing raw data
- Handling missing and invalid values
- Using exception handling for safer data processing
- Creating Python classes and methods
- Filtering records based on business conditions
- Working with sets for unique values
- Using Pandas for CSV analysis
- Exporting processed results to a text file

---

## 📈 Portfolio Roadmap

This project can be positioned as an early **Data Science / Data Analysis portfolio project**.

A possible learning progression is:

```text
Project 1 → Python Data Cleaning
Project 2 → Pandas & Exploratory Data Analysis
Project 3 → SQL Data Analysis
Project 4 → Data Visualization
Project 5 → Machine Learning
Project 6 → End-to-End Data Science Project
```

---

## 👩‍💻 Author

**Srinithi Karthikeyan**

Aspiring Data Scientist | Python | Pandas | SQL | Data Analysis | Machine Learning

---

⭐ If you find this project useful, feel free to star the repository.
