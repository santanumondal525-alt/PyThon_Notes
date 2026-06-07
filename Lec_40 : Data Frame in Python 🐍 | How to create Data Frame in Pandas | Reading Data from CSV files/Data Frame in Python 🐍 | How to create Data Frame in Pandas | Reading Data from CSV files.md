# 🐼 Pandas DataFrames
<sub>📺 <a href="https://youtu.be/HjkVu1LOvsY?si=p9dzkiYWsj6DKS5B">Video Link</a></sub>
## 🔹 What is a DataFrame?

> A **DataFrame** is a **2-dimensional labeled data structure** that stores data in **rows and columns** (tabular format), similar to a database table or Excel spreadsheet.

✅ DataFrames are part of the **Pandas library** – the most important library for **Data Science** and **Data Analytics** in Python.

---

## 🔹 Key Features of DataFrames

| Feature | Description |
|---------|-------------|
| **2D Structure** | Rows and columns (like a table) |
| **Heterogeneous** | Different columns can have different data types (int, string, float, bool) |
| **Labeled Axes** | Rows have indices, columns have names |
| **Flexible** | Can be created from dictionaries, lists, CSV files, Excel files, etc. |
| **Fast Operations** | Built-in methods for data manipulation |

---

## 🔹 Creating a DataFrame

### Method 1: Manual Creation from List of Lists

```python
import pandas as pd

student_data = [
    [1, "Varun", 30, "Male", "Chandigarh"],
    [2, "Amit", 25, "Male", "Delhi"],
    [3, "Neha", 28, "Female", "Mumbai"],
    [4, "Priya", 26, "Female", "Bengaluru"],
    [5, "Rahul", 29, "Male", "Chennai"]
]

df = pd.DataFrame(student_data, 
                  columns=["Student ID", "Name", "Age", "Gender", "Address"])

print(df)
```

**Output (Tabular Form):**

| Student ID | Name | Age | Gender | Address |
|------------|------|-----|--------|---------|
| 1 | Varun | 30 | Male | Chandigarh |
| 2 | Amit | 25 | Male | Delhi |
| 3 | Neha | 28 | Female | Mumbai |
| 4 | Priya | 26 | Female | Bengaluru |
| 5 | Rahul | 29 | Male | Chennai |

> 💡 **Syntax:** `pd.DataFrame(data, columns=[list_of_column_names])`

---

### Method 2: Loading from CSV File (Most Common in Real Life)

CSV (Comma Separated Values) files are the most common way to store and load data.

```python
import pandas as pd

# If CSV file is in the same directory as Python script
df = pd.read_csv("student.csv")

# If CSV file is outside Python environment (e.g., Desktop)
df = pd.read_csv("C:/Users/YourName/Desktop/student.csv")

print(df)
```

### Handling File Paths:

| Path Type | Example |
|-----------|---------|
| Same directory | `"student.csv"` |
| Forward slash | `"C:/Users/Name/Desktop/student.csv"` |
| Double backslash | `"C:\\Users\\Name\\Desktop\\student.csv"` |
| Raw string | `r"C:\Users\Name\Desktop\student.csv"` |

> ⚠️ **Common Issue:** Backslashes `\` can cause errors. Use forward slashes `/` or double backslashes `\\`.

---

## 🔹 Important DataFrame Attributes and Methods

### 1. `head()` – View First Few Rows

```python
df.head()      # Shows first 5 rows (default)
df.head(2)     # Shows first 2 rows
```

> ✅ Default = 5 rows if no number is specified.

### 2. `tail()` – View Last Few Rows

```python
df.tail()      # Shows last 5 rows (default)
df.tail(2)     # Shows last 2 rows
```

---

### 3. `shape` – Dimensions (Rows, Columns)

```python
print(df.shape)   # Output: (5, 5) → 5 rows, 5 columns
```

> 💡 `shape` returns a tuple: `(number_of_rows, number_of_columns)`

---

### 4. `columns` – Column Names

```python
print(df.columns)   # Output: Index(['Student ID', 'Name', 'Age', 'Gender', 'Address'], dtype='object')
```

---

### 5. `size` – Total Number of Elements

```python
print(df.size)   # Output: 25 (5 rows × 5 columns = 25 elements)
```

> 💡 `size` = rows × columns

---

### 6. `dtypes` – Data Types of Each Column

```python
print(df.dtypes)
```

**Output Example:**
```
Student ID     int64
Name          object
Age           int64
Gender        object
Address       object
dtype: object
```

| Data Type | Meaning |
|-----------|---------|
| `int64` | Integer (64-bit) |
| `object` | String/text data |
| `float64` | Floating point number |
| `bool` | Boolean (True/False) |

---

### 7. Accessing a Specific Column (Two Ways)

```python
# Method 1: Dot notation
print(df.Name)        # Returns Name column

# Method 2: Bracket notation (recommended for column names with spaces)
print(df["Name"])     # Returns Name column

# Accessing multiple columns
print(df[["Name", "Address"]])   # Returns Name and Address columns
```

---

### 8. `values` – Convert to NumPy Array

```python
print(df.values)
```

> Converts the entire DataFrame into a **2D NumPy array** (row and column values only, no labels).

---

### 9. `index` – Row Index Labels

```python
print(df.index)   # Output: RangeIndex(start=0, stop=5, step=1)
```

> 💡 By default, rows are numbered from 0 to (number_of_rows - 1).

---

## 📊 Complete Reference Table

| Attribute/Method | What it does | Example Output |
|------------------|--------------|----------------|
| `df.head(n)` | First n rows (default=5) | Displays top rows |
| `df.tail(n)` | Last n rows (default=5) | Displays bottom rows |
| `df.shape` | (rows, columns) | `(5, 5)` |
| `df.columns` | Column names | `Index(['Name', 'Age'...])` |
| `df.size` | Total elements | `25` |
| `df.dtypes` | Data types of each column | `int64`, `object`, etc. |
| `df["column"]` | Access a column | Series of values |
| `df[["col1","col2"]]` | Access multiple columns | DataFrame subset |
| `df.values` | DataFrame as NumPy array | 2D array |
| `df.index` | Row index range | `RangeIndex(start=0, stop=5, step=1)` |

---

## ✅ Important Points for Exams/Interviews

1. **DataFrame** is **2-dimensional** (rows and columns).
2. **Different columns can have different data types** – unlike NumPy arrays.
3. **`pd.read_csv()`** is the most common way to load real-world data.
4. **`head()` and `tail()`** are used to preview data without loading everything.
5. **`shape`** gives dimensions; **`size`** gives total elements.
6. **`dtypes`** shows the data type of each column.
7. **Column names** can be accessed using `df.columns`.
8. **Index** starts from `0` by default.
9. **Dot notation (`df.Name`)** works only if column name has no spaces or special characters.
10. **Bracket notation (`df["Name"]`)** is safer and works in all cases.

---

## 🧪 Practice Examples (Try Yourself)

```python
import pandas as pd

# Create a sample DataFrame
data = {
    "Product": ["A", "B", "C", "D"],
    "Price": [100, 200, 150, 250],
    "Quantity": [10, 5, 8, 3]
}
df = pd.DataFrame(data)

# Try these:
print(df.head())       # ?
print(df.shape)        # ?
print(df.columns)      # ?
print(df.size)         # ?
print(df.dtypes)       # ?
print(df["Product"])   # ?
print(df[["Product", "Price"]])  # ?
print(df.values)       # ?
print(df.index)        # ?
```

**Answers:**
- First 5 rows (all 4 rows here)
- `(4, 3)`
- `Index(['Product', 'Price', 'Quantity'], dtype='object')`
- `12` (4×3)
- `Product` → object, `Price` → int64, `Quantity` → int64
- All product names
- DataFrame with Product and Price columns
- 2D array of values
- `RangeIndex(start=0, stop=4, step=1)`

---

## 🎯 Final Pro Tips

| You want to... | Use this |
|----------------|----------|
| See top rows | `df.head()` |
| See bottom rows | `df.tail()` |
| Know dimensions | `df.shape` |
| Know column names | `df.columns` |
| Know data types | `df.dtypes` |
| Access one column | `df["column_name"]` |
| Access multiple columns | `df[["col1", "col2"]]` |
| Load CSV file | `pd.read_csv("file.csv")` |

---

## 🚀 Summary

> **DataFrame = 2D tabular data structure with labeled rows and columns**
> - Created manually or from CSV files
> - Heterogeneous data types allowed
> - `head()`, `tail()` = preview data
> - `shape` = dimensions, `size` = total elements
> - `columns` = column names, `dtypes` = data types
> - `values` = convert to NumPy array

```python
# Quick visual
import pandas as pd

# Create DataFrame
df = pd.DataFrame({
    "Name": ["A", "B", "C"],
    "Score": [85, 90, 78]
})

print(df.shape)      # (3, 2)
print(df.columns)    # Index(['Name', 'Score'])
print(df.head(2))    # First 2 rows
print(df["Name"])    # Name column
```

---

Happy Coding! 🐼📊  
You are now ready to answer any question on Pandas DataFrames in exams and interviews. 💪
