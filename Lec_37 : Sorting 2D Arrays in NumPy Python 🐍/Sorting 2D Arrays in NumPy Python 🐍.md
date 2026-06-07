# 📊 Sorting in 2D NumPy Arrays
<sub>📺 <a href="https://youtu.be/5t5hW5l0_r8?si=l9wHFHza2Wr690M0">Video Link</a></sub>
## 🔹 What is Sorting?

> Sorting arranges the elements of an array in a specific order (ascending or descending).

✅ In NumPy, sorting can be done **row-wise** or **column-wise** using the `axis` parameter.

---

## 🔹 Example 2D Array Used

```python
import numpy as np

X = np.array([[12, 11, 15],
              [21, 25, 20],
              [18, 27, 16]])
```

**Original Array X:**
```
[[12, 11, 15],
 [21, 25, 20],
 [18, 27, 16]]
```

---

# 1. `np.sort()` – Returns a Sorted Copy (Original Unchanged)

> `np.sort()` creates a **new sorted array** without modifying the original.

### Row-Wise Sorting (default) – `axis=1`

```python
sorted_copy = np.sort(X)   # or np.sort(X, axis=1)
print(sorted_copy)
```

**Output (each row sorted individually):**
```
[[11, 12, 15],
 [20, 21, 25],
 [16, 18, 27]]
```

**How it works:**
- Row 0: `[12, 11, 15]` → `[11, 12, 15]`
- Row 1: `[21, 25, 20]` → `[20, 21, 25]`
- Row 2: `[18, 27, 16]` → `[16, 18, 27]`

```python
print(X)   # Original is unchanged
```

**Output:**
```
[[12, 11, 15],
 [21, 25, 20],
 [18, 27, 16]]
```

> ✅ `np.sort()` returns a **copy**, original remains the same.

---

# 2. Column-Wise Sorting – `axis=0`

To sort **column by column** (vertically), use `axis=0`.

```python
col_sorted = np.sort(X, axis=0)
print(col_sorted)
```

**Output (each column sorted individually):**
```
[[12, 11, 15],
 [18, 25, 16],
 [21, 27, 20]]
```

**How it works:**

| Column | Original | Sorted |
|--------|----------|--------|
| Col 0 | 12, 21, 18 | 12, 18, 21 |
| Col 1 | 11, 25, 27 | 11, 25, 27 (already sorted) |
| Col 2 | 15, 20, 16 | 15, 16, 20 |

> 💡 **`axis=0`** = sort vertically (column-wise)  
> **`axis=1`** = sort horizontally (row-wise) – default

---

# 3. `array.sort()` – In-Place Sorting (Modifies Original)

> Using `array.sort()` sorts the array **in-place** – no copy is created.

```python
X.sort()   # Sorts row-wise by default (axis=1)
print(X)
```

**Output (X is now modified):**
```
[[11, 12, 15],
 [20, 21, 25],
 [16, 18, 27]]
```

### In-Place Column-Wise Sorting:
```python
X.sort(axis=0)   # Sorts column-wise
print(X)
```

> ⚠️ **Difference:** `np.sort(X)` returns a new array; `X.sort()` modifies the original.

---

# 4. `np.argsort()` – Get Sorted Indices (Not Values)

> `argsort()` returns the **indices** that would sort the array, not the sorted values themselves.

### Example – Row-wise argsort:

```python
X = np.array([[12, 11, 15],
              [21, 25, 20],
              [18, 27, 16]])

indices = np.argsort(X, axis=1)
print(indices)
```

**Output:**
```
[[1, 0, 2],
 [2, 0, 1],
 [2, 0, 1]]
```

### How to interpret:

**Row 0:** Values `[12, 11, 15]`
- Sorted order: 11 (index 1), 12 (index 0), 15 (index 2)
- Indices: `[1, 0, 2]`

**Row 1:** Values `[21, 25, 20]`
- Sorted order: 20 (index 2), 21 (index 0), 25 (index 1)
- Indices: `[2, 0, 1]`

**Row 2:** Values `[18, 27, 16]`
- Sorted order: 16 (index 2), 18 (index 0), 27 (index 1)
- Indices: `[2, 0, 1]`

> 💡 `argsort()` is useful when you need the original positions after sorting.

---

# 5. `axis` Parameter Summary

| `axis` value | Direction | Sorts |
|--------------|-----------|-------|
| `axis=0` | Vertical (down each column) | Column-wise |
| `axis=1` | Horizontal (across each row) | Row-wise (default) |

```python
np.sort(X, axis=0)   # Column-wise sort
np.sort(X, axis=1)   # Row-wise sort (default)
```

---

## 📊 Complete Reference Table

| Method | Returns | Modifies Original? | Default axis |
|--------|---------|--------------------|--------------|
| `np.sort(X)` | New sorted array | ❌ No (copy) | `axis=1` (rows) |
| `np.sort(X, axis=0)` | New sorted array (col-wise) | ❌ No | – |
| `X.sort()` | None | ✅ Yes (in-place) | `axis=1` (rows) |
| `X.sort(axis=0)` | None | ✅ Yes (in-place) | – |
| `np.argsort(X)` | Indices of sorted order | ❌ No | `axis=1` (rows) |

---

## ✅ Important Points for Exams/Interviews

1. **`np.sort()`** returns a **new sorted array** – original unchanged.
2. **`array.sort()`** modifies the **original array** in-place.
3. **Default sorting** is **row-wise** (`axis=1`).
4. **`axis=0`** = column-wise sorting.
5. **`argsort()`** returns **indices**, not values.
6. For descending order: use `np.sort(X)[::-1]` or `-np.sort(-X)`.
7. Sorting is **stable** in NumPy (preserves order of equal elements).

---

## 🧪 Practice Examples (Try Yourself)

```python
import numpy as np

arr = np.array([[30, 10, 20],
                [60, 40, 50],
                [90, 80, 70]])

# Row-wise sort (copy)
print(np.sort(arr))

# Column-wise sort (copy)
print(np.sort(arr, axis=0))

# In-place row-wise sort
arr.sort()
print(arr)

# In-place column-wise sort
arr.sort(axis=0)
print(arr)

# Argsort
print(np.argsort(arr))
```

**Answers (row-wise copy):**
```
[[10, 20, 30],
 [40, 50, 60],
 [70, 80, 90]]
```

**Answers (column-wise copy):**
```
[[30, 10, 20],
 [60, 40, 50],
 [90, 80, 70]]  # Wait, check carefully!
```

> 💡 Always verify by running the code!

---

## 🎯 Final Pro Tips

| You want to... | Use this |
|----------------|----------|
| Sort rows (keep original) | `np.sort(arr, axis=1)` |
| Sort columns (keep original) | `np.sort(arr, axis=0)` |
| Sort rows (modify original) | `arr.sort(axis=1)` |
| Sort columns (modify original) | `arr.sort(axis=0)` |
| Get sorted indices (not values) | `np.argsort(arr)` |
| Sort in descending order | `np.sort(arr)[::-1]` or `-np.sort(-arr)` |

---

## 🚀 Summary

> **Sorting in 2D NumPy Arrays**
> - **Row-wise** (`axis=1` – default) = sort each row horizontally
> - **Column-wise** (`axis=0`) = sort each column vertically
> - **`np.sort()`** = returns a **copy** (original unchanged)
> - **`array.sort()`** = **in-place** (modifies original)
> - **`np.argsort()`** = returns **indices** of sorted order

```python
# Quick visual
import numpy as np

X = np.array([[3, 1, 2],
              [6, 5, 4]])

print(np.sort(X))      # [[1,2,3], [4,5,6]] (copy)
print(np.sort(X, axis=0))  # [[3,1,2], [6,5,4]] (col-wise)
print(X)               # Original unchanged

X.sort()               # In-place row-wise
print(X)               # [[1,2,3], [4,5,6]] (modified)
```

---

Happy Coding! 🐍📊  
You are now ready to answer any question on sorting 2D NumPy arrays in exams and interviews. 💪
