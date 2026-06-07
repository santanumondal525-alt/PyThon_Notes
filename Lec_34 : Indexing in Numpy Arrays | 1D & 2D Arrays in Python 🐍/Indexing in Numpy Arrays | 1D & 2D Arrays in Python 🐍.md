# 🎯 Indexing in NumPy Arrays
<sub>📺 <a href="https://youtu.be/XLOsE-xxGN0?si=Gs51fC98twlb8ilQ">Video Link</a></sub>
## 🔹 What is Indexing?

> **Indexing** is the method of **accessing and manipulating** individual elements or groups of elements from a NumPy array.

✅ Because NumPy arrays use **contiguous memory**, indexing is very **fast** (constant time O(1)).

---

## 🔹 Why is Indexing Fast?

NumPy arrays are stored in **contiguous memory locations** (one after another).

### Memory Layout Example (1D array: [10, 20, 30, 40, 50]):

| Element | 10 | 20 | 30 | 40 | 50 |
|---------|----|----|----|----|----|
| Index | 0 | 1 | 2 | 3 | 4 |
| Memory Address | 1000 | 1004 | 1008 | 1012 | 1016 |

> 💡 If each integer takes 4 bytes, address = base_address + (index × 4).  
> Direct access – **no sequential search needed!**

---

# 1. Indexing in 1D Arrays

## Positive Indexing (left to right) – starts at `0`

```python
import numpy as np

arr = np.array([10, 20, 30, 40, 50])

print(arr[0])    # Output: 10
print(arr[1])    # Output: 20
print(arr[2])    # Output: 30
print(arr[3])    # Output: 40
print(arr[4])    # Output: 50
```

## Negative Indexing (right to left) – starts at `-1`

```python
print(arr[-1])   # Output: 50 (last element)
print(arr[-2])   # Output: 40
print(arr[-3])   # Output: 30
print(arr[-4])   # Output: 20
print(arr[-5])   # Output: 10
```

### Index Mapping:

| Positive Index | 0 | 1 | 2 | 3 | 4 |
|----------------|---|---|---|---|---|
| Negative Index | -5 | -4 | -3 | -2 | -1 |
| Value | 10 | 20 | 30 | 40 | 50 |

> ⚠️ **No index `-0`** – negative indexing starts at `-1`.

### Out of Range Error:
```python
print(arr[5])    # ❌ IndexError: index 5 is out of bounds
print(arr[-6])   # ❌ IndexError: index -6 is out of bounds
```

---

# 2. Indexing in 2D Arrays

A 2D array has **rows** and **columns**.  
Syntax: `array[row_index, column_index]`

### Example 2D Array (3×3 matrix):

```python
arr2 = np.array([[10, 20, 30],
                 [40, 50, 60],
                 [70, 80, 90]])
```

### Visual Layout:

| Row\Col | Col 0 | Col 1 | Col 2 |
|---------|-------|-------|-------|
| **Row 0** | 10 | 20 | 30 |
| **Row 1** | 40 | 50 | 60 |
| **Row 2** | 70 | 80 | 90 |

### Accessing Specific Elements:

```python
print(arr2[0, 0])   # Row 0, Col 0 → 10
print(arr2[0, 1])   # Row 0, Col 1 → 20
print(arr2[0, 2])   # Row 0, Col 2 → 30

print(arr2[1, 0])   # Row 1, Col 0 → 40
print(arr2[1, 1])   # Row 1, Col 1 → 50
print(arr2[1, 2])   # Row 1, Col 2 → 60

print(arr2[2, 0])   # Row 2, Col 0 → 70
print(arr2[2, 1])   # Row 2, Col 1 → 80
print(arr2[2, 2])   # Row 2, Col 2 → 90
```

> 🔥 **Key Rule:** First index = **row**, Second index = **column**. Both start at `0`.

---

## Special 2D Indexing – Accessing Entire Rows/Columns

### Access an Entire Row (omit column index):

```python
print(arr2[0])     # Entire row 0 → [10, 20, 30]
print(arr2[1])     # Entire row 1 → [40, 50, 60]
print(arr2[2])     # Entire row 2 → [70, 80, 90]
```

### Access an Entire Column (use `:` for all rows):

```python
print(arr2[:, 0])   # All rows, column 0 → [10, 40, 70]
print(arr2[:, 1])   # All rows, column 1 → [20, 50, 80]
print(arr2[:, 2])   # All rows, column 2 → [30, 60, 90]
```

---

## Quick 2D Indexing Reference

| Index | Meaning | Output (from example) |
|-------|---------|----------------------|
| `arr2[0, 0]` | Row 0, Col 0 | 10 |
| `arr2[1, 2]` | Row 1, Col 2 | 60 |
| `arr2[2, 1]` | Row 2, Col 1 | 80 |
| `arr2[0]` | Entire row 0 | `[10, 20, 30]` |
| `arr2[:, 1]` | Entire column 1 | `[20, 50, 80]` |

---

# 3. Memory Layout – Row-Major vs Column-Major

## Row-Major Order (Default in NumPy/C)

Elements are stored **row by row** in memory.

```
Array: [[10, 20, 30],
        [40, 50, 60],
        [70, 80, 90]]

Memory: [10, 20, 30, 40, 50, 60, 70, 80, 90]
         Row0 → Row1 → Row2
```

## Column-Major Order (Used in Fortran/MATLAB)

Elements are stored **column by column** in memory.

```
Memory: [10, 40, 70, 20, 50, 80, 30, 60, 90]
         Col0 → Col1 → Col2
```

> 💡 **Default in NumPy is Row-Major.** This affects performance for large arrays.

---

## 📊 Quick Reference Table

| Array Type | Index Example | Meaning |
|------------|---------------|---------|
| 1D positive | `arr[2]` | 3rd element (0-based) |
| 1D negative | `arr[-1]` | Last element |
| 2D element | `arr[1, 2]` | Row 1, Column 2 |
| 2D entire row | `arr[0]` | All columns of row 0 |
| 2D entire column | `arr[:, 1]` | All rows of column 1 |

---

## ✅ Important Points for Exams/Interviews

1. **Indexing starts at 0** in Python/NumPy (not 1).
2. **Negative indexing** starts at `-1` (last element) – no `-0`.
3. **2D indexing** format: `array[row, column]`.
4. **Entire row** → omit column: `array[row]`.
5. **Entire column** → use `:` for rows: `array[:, col]`.
6. **Out of range index** → `IndexError`.
7. **Contiguous memory** makes indexing **O(1)** – very fast.
8. **Row-major order** is default in NumPy (row by row in memory).

---

## 🧪 Practice Examples (Try Yourself)

```python
import numpy as np

# 1D array
arr1 = np.array([5, 10, 15, 20, 25, 30])

print(arr1[0])      # ?
print(arr1[3])      # ?
print(arr1[-1])     # ?
print(arr1[-3])     # ?

# 2D array
arr2 = np.array([[1, 2, 3],
                 [4, 5, 6],
                 [7, 8, 9]])

print(arr2[0, 2])   # ?
print(arr2[2, 0])   # ?
print(arr2[1, 1])   # ?
print(arr2[1])      # ?
print(arr2[:, 2])   # ?
```

**Answers:**
- `5`
- `20`
- `30`
- `15`
- `3`
- `7`
- `5`
- `[4, 5, 6]`
- `[3, 6, 9]`

---

## 🎯 Final Pro Tips

| You want to... | Use this |
|----------------|----------|
| First element | `arr[0]` |
| Last element | `arr[-1]` |
| Element at row r, column c | `arr[r, c]` |
| Entire row r | `arr[r]` |
| Entire column c | `arr[:, c]` |
| All elements (1D) | `arr[:]` |

---

## 🚀 Summary

> **Indexing = Direct access to array elements using position numbers**
> - 1D: `arr[index]`
> - 2D: `arr[row, col]`
> - Negative index: count from right (-1 = last)
> - Entire row: `arr[row]`
> - Entire column: `arr[:, col]`
> - Contiguous memory = Fast access (O(1))

```python
# Quick visual
import numpy as np

# 1D indexing
arr1 = np.array([10, 20, 30, 40])
print(arr1[2])     # 30
print(arr1[-2])    # 30

# 2D indexing
arr2 = np.array([[1, 2], [3, 4]])
print(arr2[1, 0])  # 3 (row 1, col 0)
print(arr2[0])     # [1, 2] (row 0)
print(arr2[:, 1])  # [2, 4] (col 1)
```

---

Happy Coding! 🐍📊  
You are now ready to answer any NumPy indexing question in exams and interviews. 💪
