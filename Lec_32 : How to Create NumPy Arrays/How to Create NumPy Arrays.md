# 📊 Creating NumPy Arrays
<sub>📺 <a href="https://youtu.be/kLVfjsfZSQE?si=d621O_5GaAjkoSzI">Video Link</a></sub>
## 🔹 Importing NumPy

By convention, NumPy is imported as `np` for brevity:

```python
import numpy as np
```

> 💡 `np` is an **alias** – you can use any name, but `np` is the standard.

---

# 1. Creating 1D Array (One-Dimensional)

## Using `np.array()` with a Python list:

```python
import numpy as np

arr1 = np.array([10, 20, 30])
print(arr1)              # Output: [10 20 30]
print(type(arr1))        # Output: <class 'numpy.ndarray'>
```

> ✅ `np.array()` converts a Python list into a NumPy array.

---

## 🔹 Important: Homogeneous Data Type (Type Casting)

NumPy arrays are **homogeneous** – all elements must be the same type.

### Case 1: All integers → integer array
```python
arr = np.array([10, 20, 30])
print(arr)   # [10 20 30]  (all int)
```

### Case 2: Mix int and float → all converted to float
```python
arr = np.array([10, 20.5, 30])
print(arr)   # [10.  20.5 30. ]  (all float)
```

### Case 3: Mix numbers and string → all converted to string
```python
arr = np.array([10, 20, "hello"])
print(arr)   # ['10' '20' 'hello']  (all string)
```

> 🔥 **Key Point:** NumPy automatically converts all elements to the **most compatible common type** (int → float → string hierarchy).

---

## 🔹 Explicitly Specifying Data Type (dtype)

You can force a specific data type using the `dtype` parameter:

```python
# Force float
arr = np.array([10, 20, 30], dtype=float)
print(arr)   # [10. 20. 30.]

# Force string (using unicode)
arr = np.array([10, 20, 30], dtype='U')  # U = Unicode string
print(arr)   # ['10' '20' '30']
```

| dtype code | Meaning |
|------------|---------|
| `int` or `'i'` | Integer |
| `float` or `'f'` | Float |
| `'U'` or `'str'` | String (Unicode) |
| `'U32'` | 32-character Unicode string |

---

# 2. Creating 2D Array (Two-Dimensional)

Pass a **nested list** (list of lists) to `np.array()`:

```python
arr2 = np.array([[10, 20, 40],
                 [78, 90, 100],
                 [110, 120, 130]])
print(arr2)
```

**Output:**
```
[[ 10  20  40]
 [ 78  90 100]
 [110 120 130]]
```

> ✅ Each inner list becomes a **row**. All rows must have the same number of columns.

---

### Indexing in 2D Array:

| Element | Access | Value (from above) |
|---------|--------|--------------------|
| Row 0, Col 0 | `arr2[0][0]` or `arr2[0,0]` | 10 |
| Row 1, Col 2 | `arr2[1][2]` or `arr2[1,2]` | 100 |
| Row 2, Col 1 | `arr2[2][1]` or `arr2[2,1]` | 120 |

> 💡 Use `arr2[row, col]` for cleaner syntax.

---

# 3. Creating Arrays Using `arange()` (Range-based)

`np.arange()` works like Python's `range()` but returns a NumPy array.

```python
arr = np.arange(1, 8)   # start=1, stop=8 (excluded)
print(arr)              # [1 2 3 4 5 6 7]
```

> ⚠️ `stop` value is **excluded** (same as Python `range()`).

---

# 4. Creating 2D Array with `arange()` + `reshape()`

`reshape()` changes the shape of an array without changing data.

```python
# Create 1D array with 6 elements
arr = np.arange(11, 17)   # [11, 12, 13, 14, 15, 16]

# Reshape to 2 rows, 3 columns
arr_2d = arr.reshape(2, 3)
print(arr_2d)
```

**Output:**
```
[[11 12 13]
 [14 15 16]]
```

> ✅ Total elements must match the shape: `2 × 3 = 6` elements.

### Common mistake – shape mismatch:
```python
# ❌ Error: cannot reshape 6 elements into 3x3 (needs 9 elements)
arr.reshape(3, 3)   # ValueError
```

### Fix – use correct number of elements:
```python
arr = np.arange(11, 20)   # 9 elements (11 to 19)
arr_2d = arr.reshape(3, 3)
```

---

# 5. Creating Arrays with `zeros()` and `ones()`

## `zeros()` – Array filled with zeros

```python
# 1D array of 5 zeros
zeros_1d = np.zeros(5)
print(zeros_1d)   # [0. 0. 0. 0. 0.]

# 2D array: 4 rows, 2 columns (all zeros)
zeros_2d = np.zeros((4, 2))
print(zeros_2d)
```

**Output (4×2 zeros):**
```
[[0. 0.]
 [0. 0.]
 [0. 0.]
 [0. 0.]]
```

## `ones()` – Array filled with ones

```python
# 1D array of 3 ones
ones_1d = np.ones(3)
print(ones_1d)   # [1. 1. 1.]

# 2D array: 2 rows, 3 columns (all ones)
ones_2d = np.ones((2, 3))
print(ones_2d)
```

**Output:**
```
[[1. 1. 1.]
 [1. 1. 1.]]
```

> 💡 By default, `zeros()` and `ones()` create **float** arrays. Use `dtype=int` for integers.

---

## 📊 Complete Reference Table

| Method | Example | Output |
|--------|---------|--------|
| `np.array([1,2,3])` | 1D array | `[1 2 3]` |
| `np.array([[1,2],[3,4]])` | 2D array (2×2) | `[[1 2][3 4]]` |
| `np.arange(1, 8)` | 1 to 7 | `[1 2 3 4 5 6 7]` |
| `np.arange(11,17).reshape(2,3)` | 2×3 array | `[[11 12 13][14 15 16]]` |
| `np.zeros(5)` | 1D zeros | `[0. 0. 0. 0. 0.]` |
| `np.zeros((4,2))` | 4×2 zeros | 4 rows, 2 columns of zeros |
| `np.ones(3)` | 1D ones | `[1. 1. 1.]` |
| `np.ones((2,3))` | 2×3 ones | 2 rows, 3 columns of ones |

---

## ✅ Important Points for Exams/Interviews

1. **`np.array()`** converts Python list to NumPy array.
2. **NumPy arrays are homogeneous** – all elements same type (auto-converted).
3. **`dtype` parameter** – explicitly set data type.
4. **`np.arange(start, stop)`** – stop is **excluded**.
5. **`reshape()`** changes array shape without changing data.
6. **`reshape()` requires total elements to match** the new shape.
7. **`np.zeros(shape)`** – shape as tuple for multi-dimensional `(rows, cols)`.
8. **`np.ones(shape)`** – same as zeros but filled with 1s.
9. **Default dtype** for `zeros()`/`ones()` is `float64`.
10. **2D array indexing** – `array[row, col]`.

---

## 🧪 Practice Examples (Try Yourself)

```python
import numpy as np

# 1. Create 1D array
arr1 = np.array([5, 10, 15])
print(arr1)

# 2. Create 2D array
arr2 = np.array([[1, 2], [3, 4], [5, 6]])
print(arr2.shape)   # (3, 2)

# 3. Auto type conversion
arr3 = np.array([1, 2.5, 3])
print(arr3.dtype)   # float64

# 4. arange with reshape
arr4 = np.arange(1, 10).reshape(3, 3)
print(arr4)

# 5. Zeros and ones
zeros = np.zeros((2, 2), dtype=int)
ones = np.ones((2, 2), dtype=int)
print(zeros)
print(ones)
```

---

## 🎯 Final Pro Tips

| You want to... | Use this |
|----------------|----------|
| Create array from list | `np.array(list)` |
| Create sequence of numbers | `np.arange(start, stop)` |
| Change array shape | `.reshape(rows, cols)` |
| Create array of zeros | `np.zeros(shape)` |
| Create array of ones | `np.ones(shape)` |
| Force specific data type | `dtype=type` parameter |
| Check array shape | `.shape` attribute |
| Check data type | `.dtype` attribute |

---

## 🚀 Summary

> **Creating NumPy Arrays:**
> - `np.array(list)` – from Python list
> - `np.arange(start, stop)` – range-based
> - `np.zeros(shape)` – all zeros
> - `np.ones(shape)` – all ones
> - `.reshape()` – change dimensions
> - **Homogeneous** – all elements same type (auto-converted)

```python
# Quick visual
import numpy as np

arr = np.array([1, 2, 3])              # 1D
arr = np.array([[1,2],[3,4]])          # 2D
arr = np.arange(1, 10).reshape(3, 3)   # 3x3 matrix
zeros = np.zeros((4, 2))               # 4x2 zeros
ones = np.ones(5)                      # 5 ones
```

---

Happy Coding! 🐍📊  
You are now ready to create NumPy arrays for exams and interviews. 💪
