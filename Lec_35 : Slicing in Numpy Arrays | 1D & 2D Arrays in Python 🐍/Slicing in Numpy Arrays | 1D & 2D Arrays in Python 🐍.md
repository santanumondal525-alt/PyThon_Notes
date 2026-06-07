# ✂️ Slicing in NumPy Arrays
<sub>📺 <a href="https://youtu.be/atG-l8VI8z4?si=z6sp_L0iUO0iA4Lf">Video Link</a></sub>
## 🔹 What is Slicing?

> **Slicing** is the method of extracting a **subset** (group/collection) of elements from an array, rather than just a single element.

✅ While **indexing** gets one element, **slicing** gets multiple elements at once.

---

## 🔹 Slicing Syntax

```python
array[start : stop : step]
```

| Parameter | Meaning | Default |
|-----------|---------|---------|
| `start` | Index to begin (included) | 0 |
| `stop` | Index to stop (**excluded**) | end of array |
| `step` | Jump size (how many elements to skip) | 1 |

> 🔥 **Most Important Rule:** `stop` index is **always excluded** – the element at `stop` is NOT included.

---

# 1. Slicing in 1D Arrays

### Example Array:
```python
import numpy as np
arr = np.array([10, 20, 30, 40, 50, 60, 70])
```

### Index Mapping (Positive):

| Index | 0 | 1 | 2 | 3 | 4 | 5 | 6 |
|-------|---|---|---|---|---|---|---|
| Value | 10 | 20 | 30 | 40 | 50 | 60 | 70 |

### Index Mapping (Negative):

| Negative Index | -7 | -6 | -5 | -4 | -3 | -2 | -1 |
|----------------|----|----|----|----|----|----|----|
| Value | 10 | 20 | 30 | 40 | 50 | 60 | 70 |

---

## 1D Slicing Examples

| Slice | Meaning | Output |
|-------|---------|--------|
| `arr[1:4]` | Start=1, Stop=4 (excluded) → indices 1,2,3 | `[20, 30, 40]` |
| `arr[1:6]` | Start=1, Stop=6 (excluded) → indices 1 to 5 | `[20, 30, 40, 50, 60]` |
| `arr[1:6:2]` | Start=1, Stop=6 (excluded), Step=2 → skip every other | `[20, 40, 60]` |
| `arr[:4]` | Start=0 (default), Stop=4 → indices 0,1,2,3 | `[10, 20, 30, 40]` |
| `arr[3:]` | Start=3, Stop=end (default) → indices 3 to 6 | `[40, 50, 60, 70]` |
| `arr[:]` | Entire array | `[10, 20, 30, 40, 50, 60, 70]` |
| `arr[::2]` | Step=2, entire array → take every 2nd element | `[10, 30, 50, 70]` |

---

## 1D Slicing with Negative Indices

| Slice | Meaning | Output |
|-------|---------|--------|
| `arr[-4:-1]` | Start=-4 (index 3), Stop=-1 (index 6 excluded) → indices 3,4,5 | `[40, 50, 60]` |
| `arr[-3:]` | Start=-3 (index 4), Stop=end | `[50, 60, 70]` |
| `arr[:-2]` | Start=0, Stop=-2 (index 5 excluded) → indices 0 to 4 | `[10, 20, 30, 40, 50]` |

> ⚠️ Negative stop index is also **excluded**!

---

## Reversing an Array using Slicing

```python
arr_rev = arr[::-1]
print(arr_rev)   # [70, 60, 50, 40, 30, 20, 10]
```

> 💡 `[::-1]` = start from end, move backwards with step -1 (full reverse)

---

# 2. Slicing in 2D Arrays

### Example 2D Array (4 rows × 3 columns):
```python
arr2 = np.array([[15, 16, 17],
                 [25, 26, 27],
                 [35, 36, 37],
                 [45, 46, 47]])
```

### Visual Layout with Indices:

| Row\Col | Col 0 | Col 1 | Col 2 |
|---------|-------|-------|-------|
| **Row 0** | 15 | 16 | 17 |
| **Row 1** | 25 | 26 | 27 |
| **Row 2** | 35 | 36 | 37 |
| **Row 3** | 45 | 46 | 47 |

> Shape = `(4, 3)` → 4 rows, 3 columns

---

## 2D Slicing Syntax

```python
array[row_start:row_stop, col_start:col_stop]
```

> 💡 **First bracket = rows**, **Second bracket = columns** (after comma)

---

## 2D Slicing Examples

### Extract a Single Row:
```python
print(arr2[1])      # Row 1 → [25, 26, 27]
print(arr2[1, :])   # Same as above (explicit)
```

### Extract a Single Column:
```python
print(arr2[:, 1])   # Column 1 (all rows) → [16, 26, 36, 46]
```

### Extract a Subset (Rows 1-2, Columns 0-1):
```python
print(arr2[1:3, 0:2])
```
- Rows: 1 and 2 (since stop=3 excluded)
- Columns: 0 and 1 (since stop=2 excluded)

**Output:**
```
[[25, 26],
 [35, 36]]
```

### Extract Entire Rows (Row 1 to end):
```python
print(arr2[1:, :])   # All columns, rows 1,2,3
```

**Output:**
```
[[25, 26, 27],
 [35, 36, 37],
 [45, 46, 47]]
```

---

## 2D Slicing with Step

### Every 2nd row, all columns:
```python
print(arr2[::2, :])
```
**Output:** Rows 0 and 2 → `[[15,16,17], [35,36,37]]`

### Every 2nd column, all rows:
```python
print(arr2[:, ::2])
```
**Output:** Columns 0 and 2 → `[[15,17], [25,27], [35,37], [45,47]]`

---

## 2D Slicing – More Examples

| Slice | Meaning | Output |
|-------|---------|--------|
| `arr2[1:3, 1:3]` | Rows 1-2, Cols 1-2 | `[[26,27], [36,37]]` |
| `arr2[:2, 1:]` | Rows 0-1, Cols 1 to end | `[[16,17], [26,27]]` |
| `arr2[2:, :2]` | Rows 2 to end, Cols 0-1 | `[[35,36], [45,46]]` |
| `arr2[1, 1:3]` | Row 1, Cols 1-2 | `[26, 27]` |
| `arr2[:2, 2]` | Rows 0-1, Column 2 | `[17, 27]` |
| `arr2[1:3, 0]` | Rows 1-2, Column 0 | `[25, 35]` |

---

## 📊 Complete Quick Reference Table

| Operation | 1D Syntax | 2D Syntax |
|-----------|-----------|-----------|
| Single element | `arr[i]` | `arr[r, c]` |
| Start to stop-1 | `arr[s:st]` | `arr[sr:st, :]` or `arr[:, sc:stc]` |
| Entire array | `arr[:]` | `arr[:, :]` |
| With step | `arr[s:st:step]` | `arr[sr:st:step, sc:stc:step]` |
| Reverse | `arr[::-1]` | `arr[::-1, ::-1]` |
| All rows, specific cols | – | `arr[:, c1:c2]` |
| Specific rows, all cols | – | `arr[r1:r2, :]` |

---

## ✅ Important Points for Exams/Interviews

1. **`stop` index is always excluded** – this is the most common mistake!
2. **Default start = 0**, **default stop = end**, **default step = 1**.
3. **Negative step** reverses direction (`[::-1]` reverses the array).
4. **2D slicing format:** `array[rows, columns]`
5. **`:` alone** means "all" (all rows or all columns).
6. **No error** if stop is beyond array length – returns up to end.
7. **Slicing creates a view** (not a copy) by default in NumPy.

---

## 🧪 Practice Examples (Try Yourself)

```python
import numpy as np

# 1D array
arr1 = np.array([5, 10, 15, 20, 25, 30, 35])

print(arr1[2:5])      # ?
print(arr1[:4])       # ?
print(arr1[3:])       # ?
print(arr1[::3])      # ?
print(arr1[-4:-1])    # ?
print(arr1[::-2])     # ?

# 2D array
arr2 = np.array([[1, 2, 3, 4],
                 [5, 6, 7, 8],
                 [9, 10, 11, 12]])

print(arr2[1, 1:3])   # ?
print(arr2[:2, 2:])   # ?
print(arr2[::2, ::2]) # ?
print(arr2[:, 1:3])   # ?
print(arr2[1:, 0])    # ?
```

**Answers:**
- `[15, 20, 25]`
- `[5, 10, 15, 20]`
- `[20, 25, 30, 35]`
- `[5, 20, 35]`
- `[20, 25, 30]`
- `[35, 25, 15, 5]`
- `[6, 7]`
- `[[3, 4], [7, 8]]`
- `[[1, 3], [9, 11]]`
- `[[2, 3], [6, 7], [10, 11]]`
- `[5, 9]`

---

## 🎯 Final Pro Tips

| You want to... | Use this |
|----------------|----------|
| First 3 elements | `arr[:3]` |
| Last 3 elements | `arr[-3:]` |
| Elements 2 to 5 | `arr[2:6]` (stop=6 excluded) |
| Every 2nd element | `arr[::2]` |
| Reverse array | `arr[::-1]` |
| Specific rows, all columns | `arr[r1:r2, :]` |
| All rows, specific columns | `arr[:, c1:c2]` |
| Specific submatrix | `arr[r1:r2, c1:c2]` |

---

## 🚀 Summary

> **Slicing = Extracting subsets using [start:stop:step]**
> - `start` = included
> - `stop` = excluded (very important!)
> - `step` = jump size
> - `:` alone = all elements
> - `::-1` = reverse
> - 2D format: `[row_start:row_stop, col_start:col_stop]`

```python
# Quick visual
import numpy as np

arr = np.array([10, 20, 30, 40, 50, 60])

print(arr[1:4])    # [20, 30, 40]  (stop=4 excluded)
print(arr[::2])    # [10, 30, 50]
print(arr[::-1])   # [60, 50, 40, 30, 20, 10]

# 2D
mat = np.array([[1,2,3],[4,5,6],[7,8,9]])
print(mat[:2, 1:]) # [[2,3], [5,6]]
```

---

Happy Coding! 🐍📊  
You are now ready to answer any NumPy slicing question in exams and interviews. 💪
