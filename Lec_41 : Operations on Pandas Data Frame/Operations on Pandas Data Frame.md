# 🐼 DataFrame Operations
<sub>📺 <a href="https://youtu.be/cFhlU4eR6EU?si=1xSokJglPajlNJs-">Video Link</a></sub>
## 🔹 What are DataFrame Operations?

> DataFrame operations allow you to **manipulate** data in tabular form – similar to SQL commands (SELECT, INSERT, UPDATE, DELETE).

✅ You can **select, add, update, and delete** both rows and columns.

---

## 🔹 Sample DataFrame Used

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
```

**DataFrame:**
| Student ID | Name | Age | Gender | Address |
|------------|------|-----|--------|---------|
| 1 | Varun | 30 | Male | Chandigarh |
| 2 | Amit | 25 | Male | Delhi |
| 3 | Neha | 28 | Female | Mumbai |
| 4 | Priya | 26 | Female | Bengaluru |
| 5 | Rahul | 29 | Male | Chennai |

> 💡 **Row Index:** 0, 1, 2, 3, 4 (starts at 0)  
> **Column Index:** 0, 1, 2, 3, 4

---

# 1. SELECTING Data

## 1.1 Select a Single Column

```python
print(df["Name"])      # Returns Name column (Series)
print(df.Name)         # Alternative (dot notation - works if no spaces)
```

**Output:** All names: Varun, Amit, Neha, Priya, Rahul

## 1.2 Select Multiple Columns

```python
print(df[["Name", "Address"]])   # Double brackets for multiple columns
```

## 1.3 Select a Single Row by Index (using `.loc[]`)

```python
print(df.loc[0])    # Row at index 0 (first row)
print(df.loc[2])    # Row at index 2 (third row)
```

> 💡 `.loc[]` is label-based indexing (uses row index labels).

## 1.4 Select Multiple Rows by Index

```python
print(df.loc[[0, 2, 4]])   # Rows at indices 0, 2, and 4
```

## 1.5 Select a Single Row by Position (using `.iloc[]`)

```python
print(df.iloc[1])   # Row at integer position 1 (second row)
```

> 💡 `.iloc[]` is integer position-based indexing (0, 1, 2...).

---

# 2. FILTERING Data (Condition-based Selection)

Similar to SQL's `WHERE` clause.

```python
# Select rows where Age > 29
filtered_df = df[df["Age"] > 29]
print(filtered_df)
```

**Output:** Only rows with Age > 29 (Varun with Age 30)

| Student ID | Name | Age | Gender | Address |
|------------|------|-----|--------|---------|
| 1 | Varun | 30 | Male | Chandigarh |

---

# 3. ADDING a New Column

## 3.1 Add a New Column at the End (Default)

```python
df["Phone"] = ["1234567890", "9876543210", "5555555555", "4444444444", "3333333333"]
print(df)
```

> 💡 New column is added at the **end** (rightmost).

## 3.2 Add a Column with Same Value for All Rows

```python
df["Country"] = "India"   # All rows get "India"
```

---

# 4. INSERTING a Column at a Specific Position

Using `df.insert(location, column_name, values)`

```python
# Insert "Phone" column at position 3 (after Gender)
df.insert(3, "Phone", ["1234567890", "9876543210", "5555555555", "4444444444", "3333333333"])
print(df)
```

**Parameter explanation:**
- `3` = column index (0-based) – inserts before existing column at index 3
- `"Phone"` = name of new column
- `[values]` = list of values for each row

> 💡 Positions: 0=Student ID, 1=Name, 2=Age, **3=Phone (new)**, 4=Gender, 5=Address

---

# 5. RENAMING a Column

Using `df.rename(columns={"old_name": "new_name"})`

```python
df.rename(columns={"Age": "Student Age"}, inplace=True)
print(df)
```

> ⚠️ `inplace=True` modifies the original DataFrame. Without it, returns a copy.

---

# 6. DELETING a Column

## Method 1: Using `df.drop()`

```python
df.drop(columns=["Phone"], inplace=True)
```

## Method 2: Using `del`

```python
del df["Phone"]
```

## Delete Multiple Columns

```python
df.drop(columns=["Phone", "Country"], inplace=True)
```

---

# 7. DELETING a Row

Using `df.drop(index=row_index)`

```python
# Delete row at index 4 (fifth row)
df.drop(index=4, inplace=True)
print(df)
```

> 💡 After deletion, the DataFrame no longer has that row.

---

# 8. ADDING a New Row

Using `df.loc[index]` to add a row at a specific index.

```python
df.loc[4] = [6, "Pinky", 24, "Female", "Bangalore", "9999999999", "India"]
print(df)
```

> 💡 If index 4 already exists, it **updates** it. If it doesn't exist, it **adds** a new row.

---

# 9. UPDATING Values

## 9.1 Update a Single Value

```python
# Update Age at index 2 (third row) to 71
df.loc[2, "Age"] = 71
print(df)
```

## 9.2 Update Multiple Values (Multiple Rows and Columns)

```python
# Update Address at index 0 and index 2
df.loc[[0, 2], "Address"] = ["Andaman", "Nicobar"]
print(df)
```

> 💡 `.loc[row_index_list, column_name]` = update specific cells.

---

## 📊 Complete Reference Table

| Operation | Method | Example |
|-----------|--------|---------|
| Select column | `df["col"]` | `df["Name"]` |
| Select multiple columns | `df[["col1","col2"]]` | `df[["Name","Age"]]` |
| Select row by label | `df.loc[index]` | `df.loc[2]` |
| Select multiple rows | `df.loc[[i1,i2]]` | `df.loc[[0,2,4]]` |
| Select row by position | `df.iloc[pos]` | `df.iloc[1]` |
| Filter rows | `df[condition]` | `df[df["Age"] > 29]` |
| Add column (end) | `df["new"] = values` | `df["Phone"] = [...]` |
| Insert column at position | `df.insert(pos, "name", values)` | `df.insert(3, "Phone", [...])` |
| Rename column | `df.rename(columns={"old":"new"})` | `df.rename(columns={"Age":"Student Age"})` |
| Delete column | `df.drop(columns=["col"])` | `df.drop(columns=["Phone"])` |
| Delete row | `df.drop(index=[i])` | `df.drop(index=4)` |
| Add new row | `df.loc[index] = [...]` | `df.loc[5] = [values]` |
| Update single value | `df.loc[row, "col"] = value` | `df.loc[2, "Age"] = 71` |
| Update multiple values | `df.loc[[rows], "col"] = [values]` | `df.loc[[0,2], "Address"] = ["A","N"]` |

---

## ✅ Important Points for Exams/Interviews

1. **`.loc[]`** – label-based indexing (uses row index labels).
2. **`.iloc[]`** – integer position-based indexing (0, 1, 2...).
3. **`df["column"]`** – selects a single column as a Series.
4. **`df[["col1","col2"]]`** – double brackets for multiple columns.
5. **`df[condition]`** – filters rows based on a condition (like SQL WHERE).
6. **`df.insert(pos, name, values)`** – adds column at specific position.
7. **`inplace=True`** – modifies the original DataFrame (otherwise returns a copy).
8. **`df.drop()`** – can delete both rows and columns.
9. **`df.loc[index] = values`** – adds new row if index doesn't exist.
10. **Row indices start at 0** – always remember this!

---

## 🧪 Practice Examples (Try Yourself)

```python
import pandas as pd

df = pd.DataFrame({
    "Product": ["A", "B", "C"],
    "Price": [100, 200, 150],
    "Stock": [10, 5, 8]
})

# 1. Select Price column
print(df["Price"])

# 2. Select Product and Stock columns
print(df[["Product", "Stock"]])

# 3. Select row at index 1
print(df.loc[1])

# 4. Filter where Price > 120
print(df[df["Price"] > 120])

# 5. Add new column 'Discount' with value 10 for all rows
df["Discount"] = 10
print(df)

# 6. Insert 'Category' column at position 1
df.insert(1, "Category", ["X", "Y", "Z"])
print(df)

# 7. Update Price at index 0 to 120
df.loc[0, "Price"] = 120
print(df)

# 8. Delete Stock column
df.drop(columns=["Stock"], inplace=True)
print(df)

# 9. Delete row at index 2
df.drop(index=2, inplace=True)
print(df)
```

---

## 🎯 Final Pro Tips

| You want to... | Use this |
|----------------|----------|
| Get one column | `df["column"]` |
| Get multiple columns | `df[["col1", "col2"]]` |
| Get one row by index | `df.loc[index]` |
| Filter rows | `df[df["col"] > value]` |
| Add column at end | `df["new"] = values` |
| Add column at specific position | `df.insert(pos, "name", values)` |
| Rename column | `df.rename(columns={"old":"new"})` |
| Delete column | `df.drop(columns=["col"])` |
| Delete row | `df.drop(index=[i])` |
| Update a cell | `df.loc[row, "col"] = value` |

---

## 🚀 Summary

> **DataFrame Operations = SELECT, INSERT, UPDATE, DELETE**
> - **Select**: `df["col"]`, `df.loc[row]`, `df[condition]`
> - **Add column**: `df["new"] = values` or `df.insert()`
> - **Update**: `df.loc[row, "col"] = value`
> - **Delete column**: `df.drop(columns=["col"])`
> - **Delete row**: `df.drop(index=[i])`

```python
# Quick visual
import pandas as pd

df = pd.DataFrame({"Name": ["A", "B"], "Score": [85, 90]})

# Select
print(df["Name"])           # A, B
print(df.loc[0])            # A, 85

# Add column
df["Grade"] = ["A", "A+"]   # New column at end

# Update
df.loc[0, "Score"] = 88     # Change A's score to 88

# Delete
df.drop(columns=["Grade"], inplace=True)
df.drop(index=1, inplace=True)  # Remove row B
```

---

Happy Coding! 🐼📊  
You are now ready to answer any DataFrame manipulation question in exams and interviews. 💪
