# 📊 Student Marks Analysis using Pandas

This project demonstrates basic data analysis operations using the **Pandas** library in Python. It includes data cleaning, filtering, statistical operations, and column manipulation.

---

## 📁 Dataset

We have a simple dataset of students with the following fields:

- `Name`: Student's name
- `Marks`: Marks obtained out of 100
- `Gender`: Gender of the student

---

## 🧠 Key Operations Performed

- Display top and bottom rows of the dataset
- Shape and structure of the DataFrame
- Null value detection (row-wise and column-wise)
- Summary statistics using `describe()`
- Unique values and value counts
- Filtering with conditions (like marks between 90-100)
- Calculating average marks
- Using `apply()` and `map()` functions
- Adding and dropping columns
- Sorting DataFrame
- Filtering female students' records

---

## 💻 Code Snippet

```python
import pandas as pd

# Creating DataFrame
data = {
    'Name': ['Priyang', 'Aadhya', 'Krisha', 'Vedant', 'Parshv', 'Mittal', 'Archana'],
    'Marks': [98, 89, 99, 87, 90, 83, 99],
    'Gender': ['Male', 'Female', 'Female', 'Male', 'Male', 'Female', 'Female']
}
df = pd.DataFrame(data)

# Display basic info
print(df.head())
print("Shape:", df.shape)

# Null check
print(df.isnull().sum())

# Summary stats
print(df.describe())

# Unique and count in Gender
print(df['Gender'].unique())
print(df['Gender'].value_counts())

# Students with marks between 90 and 100
filtered_df = df[df['Marks'].between(90, 100)]
print(filtered_df)

# Add Half Marks column
df['Half Marks'] = df['Marks'].apply(lambda x: x / 2)

# Map Gender to Binary
df['Male_Female'] = df['Gender'].map({'Male': 1, 'Female': 0})

# Drop columns
df.drop(['Half Marks', 'Male_Female'], axis=1, inplace=True)

# Sort by Marks
print(df.sort_values('Marks', ascending=False))

# Filter Female Students
print(df[df['Gender'] == 'Female'][['Name', 'Marks']])
# Marks-
