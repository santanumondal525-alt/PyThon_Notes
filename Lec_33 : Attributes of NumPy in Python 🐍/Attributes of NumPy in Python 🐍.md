# 📊 NumPy Array Attributes
<sub>📺 <a href="https://youtu.be/Aff6Z0Pz650?si=p8pq_PpdQKVltZY1">Video Link</a></sub>
## 🔹 What are Attributes?

> **Attributes** are properties of a NumPy array that give you **information about the array** – its dimensions, shape, size, data type, and memory usage.

✅ Attributes are accessed using **dot notation**: `array.attribute`

---

## 🔹 The 5 Most Important NumPy Array Attributes

| Attribute | Meaning | What it tells you |
|-----------|---------|--------------------|
| `ndim` | Number of dimensions | 1D, 2D, 3D, etc. |
| `shape` | Shape of array | Rows, columns, layers |
| `size` | Total number of elements | Count of all elements |
| `dtype` | Data type | int, float, string, etc. |
| `itemsize` | Memory per element | Bytes per element |

---

# 1. `ndim` – Number of Dimensions 🔢

Returns the **number of dimensions** (axes) of the array.

```python
import numpy as np

# 1D array
arr1 = np.array([10, 20, 30])
print(arr1.ndim)   # Output: 1

# 2D array
arr2 = np.array([[10, 20, 30],
                 [40, 50, 60]])
print(arr2.ndim)   # Output: 2

# 3D array
arr3 = np.array([[[1, 2], [3, 4]], [[5, 6], [7, 8]]])
print(arr3.ndim)   # Output: 3
```

> 💡 You can also count the number of opening brackets `[` to guess dimensions.

---

# 2. `shape` – Shape of Array 📐

Returns a **tuple** representing the size of each dimension.

| Array Type | Shape Output | Meaning |
|------------|--------------|---------|
| 1D array with 5 elements | `(5,)` | 5 elements in 1 dimension |
| 2D array with 3 rows, 3 columns | `(3, 3)` | 3 × 3 matrix |
| 3D array with 2 layers, 2 rows, 3 columns | `(2, 2, 3)` | 2 layers × 2 rows × 3 columns |

### Examples:

```python
# 1D array
arr1 = np.array([10, 20, 30, 40, 50])
print(arr1.shape)   # Output: (5,)

# 2D array (3 rows, 3 columns)
arr2 = np.array([[10, 20, 30],
                 [40, 50, 60],
                 [70, 80, 90]])
print(arr2.shape)   # Output: (3, 3)

# 3D array (2 layers, 2 rows, 3 columns)
arr3 = np.array([
    [[1, 2, 3], [4, 5, 6]],
    [[7, 8, 9], [10, 11, 12]]
])
print(arr3.shape)   # Output: (2, 2, 3)
```

> 🔥 **Understanding 3D shape `(2, 2, 3)`:**  
> - First number (2) = number of **layers** (depth)  
> - Second number (2) = number of **rows**  
> - Third number (3) = number of **columns**

---

# 3. `size` – Total Number of Elements 🔢

Returns the **total number of elements** in the array.

```python
# 2D array: 3 rows × 3 columns = 9 elements
arr2 = np.array([[10, 20, 30],
                 [40, 50, 60],
                 [70, 80, 90]])
print(arr2.size)   # Output: 9

# 3D array: 2 × 2 × 3 = 12 elements
arr3 = np.array([
    [[1, 2, 3], [4, 5, 6]],
    [[7, 8, 9], [10, 11, 12]]
])
print(arr3.size)   # Output: 12
```

> 💡 `size` = product of all numbers in `shape` (e.g., 2 × 2 × 3 = 12)

---

# 4. `dtype` – Data Type of Elements 🏷️

Returns the **data type** of elements in the array (all elements have same type – homogeneous).

```python
# Integer array
arr_int = np.array([1, 2, 3])
print(arr_int.dtype)   # Output: int32 (or int64 depending on system)

# Float array
arr_float = np.array([1.5, 2.5, 3.5])
print(arr_float.dtype) # Output: float64

# String array
arr_str = np.array(['a', 'b', 'c'])
print(arr_str.dtype)   # Output: <U1 (Unicode string)

# Array with mixed int and float → all converted to float
arr_mixed = np.array([1, 2.5, 3])
print(arr_mixed.dtype) # Output: float64
```

### Common dtype values:

| dtype | Meaning | Bits |
|-------|---------|------|
| `int32` | Integer | 32 bits (4 bytes) |
| `int64` | Integer | 64 bits (8 bytes) |
| `float32` | Float (single precision) | 32 bits (4 bytes) |
| `float64` | Float (double precision) | 64 bits (8 bytes) |
| `<U1` | Unicode string (1 char) | Depends |
| `bool` | Boolean (True/False) | 1 byte |

---

# 5. `itemsize` – Memory Size Per Element 💾

Returns the **size (in bytes)** of each individual element.

```python
# Integer array – typically 4 or 8 bytes
arr_int = np.array([1, 2, 3])
print(arr_int.dtype)      # int32
print(arr_int.itemsize)   # Output: 4 (bytes)

# Float array – typically 8 bytes
arr_float = np.array([1.5, 2.5, 3.5])
print(arr_float.dtype)    # float64
print(arr_float.itemsize) # Output: 8 (bytes)
```

> 💡 **Relationship:** `itemsize` × `size` = total memory used by array data

---

## 📊 Complete Reference Table

| Attribute | What it does | Example (2D array: 3×3 integers) | Output |
|-----------|--------------|-----------------------------------|--------|
| `ndim` | Number of dimensions | `arr.ndim` | `2` |
| `shape` | Size of each dimension | `arr.shape` | `(3, 3)` |
| `size` | Total elements | `arr.size` | `9` |
| `dtype` | Data type of elements | `arr.dtype` | `int32` |
| `itemsize` | Bytes per element | `arr.itemsize` | `4` |

---

## ✅ Important Points for Exams/Interviews

1. **`ndim`** – number of axes/dimensions (1D=1, 2D=2, 3D=3, etc.)
2. **`shape`** – returns a tuple; length of tuple = `ndim`
3. **`size`** = product of all numbers in `shape`
4. **`dtype`** – all NumPy array elements have the **same data type** (homogeneous)
5. **`itemsize`** – memory per element in bytes
6. Total memory = `size × itemsize` (plus small overhead)
7. **1D array shape** has a comma: `(5,)` – not just `(5)`

---

## 🧪 Practice Examples (Try Yourself)

```python
import numpy as np

# Create different arrays
arr1 = np.array([1, 2, 3, 4, 5])
arr2 = np.array([[1, 2], [3, 4], [5, 6]])
arr3 = np.zeros((2, 3, 4))
arr4 = np.array([1.1, 2.2, 3.3])

# Test your knowledge
print(arr1.ndim)      # ?
print(arr1.shape)     # ?
print(arr1.size)      # ?
print(arr1.dtype)     # ?
print(arr1.itemsize)  # ?

print(arr2.ndim)      # ?
print(arr2.shape)     # ?
print(arr2.size)      # ?

print(arr3.ndim)      # ?
print(arr3.shape)     # ?
print(arr3.size)      # ?

print(arr4.dtype)     # ?
print(arr4.itemsize)  # ?
```

**Answers:**
- `arr1`: ndim=1, shape=(5,), size=5, dtype=int32/64, itemsize=4/8
- `arr2`: ndim=2, shape=(3, 2), size=6
- `arr3`: ndim=3, shape=(2, 3, 4), size=24
- `arr4`: dtype=float64, itemsize=8

---

## 🎯 Final Pro Tips

| You want to know... | Use this attribute |
|---------------------|--------------------|
| How many dimensions? | `ndim` |
| Rows and columns? | `shape` |
| Total elements? | `size` |
| Type of data stored? | `dtype` |
| Memory per element? | `itemsize` |
| Total memory used? | `size × itemsize` |

---

## 🚀 Summary

> **NumPy Array Attributes = Array's Identity Card**
> - `ndim` = dimensions (1, 2, 3...)
> - `shape` = size of each dimension as tuple
> - `size` = total number of elements
> - `dtype` = data type (int, float, string...)
> - `itemsize` = bytes per element

```python
# Quick visual
import numpy as np

arr = np.array([[1, 2, 3],
                [4, 5, 6]])

print(arr.ndim)     # 2
print(arr.shape)    # (2, 3)
print(arr.size)     # 6
print(arr.dtype)    # int64 (or int32)
print(arr.itemsize) # 8 (or 4)
```

---

Happy Coding! 🐍📊  
You are now ready to answer any question about NumPy array attributes in exams and interviews. 💪
