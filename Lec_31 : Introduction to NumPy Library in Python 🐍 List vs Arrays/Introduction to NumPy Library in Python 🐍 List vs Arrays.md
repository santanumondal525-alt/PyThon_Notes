# 📊 NumPy Arrays in Python
<sub>📺 <a href="https://youtu.be/ceMMJZrAXl8?si=OMgtELBF8yFjp5Fi">Video Link</a></sub>
## 🔹 What is NumPy?

> **NumPy** = **Numerical Python**

It is a **powerful Python library** used for:
- Scientific computing
- Data analysis
- Data science
- Machine learning
- Image processing
- Heavy numerical computations

✅ NumPy makes complex mathematical operations **very fast and efficient**.

---

## 🔹 How to Install NumPy

```bash
pip install numpy
```

Other related libraries (for data science):
```bash
pip install pandas
pip install matplotlib
```

---

## 🔹 The Core Object: `ndarray` (n-dimensional array)

> **ndarray** = N-dimensional array

NumPy arrays are **multi-dimensional** containers for storing homogeneous data.

| Dimension | Name | Shape |
|-----------|------|-------|
| 1D | Vector | (n,) |
| 2D | Matrix | (rows, columns) |
| 3D | Tensor | (depth, rows, columns) |
| nD | ndarray | Any shape |

---

## 🔹 Key Properties of NumPy Arrays

| Property | Meaning |
|----------|---------|
| **Homogeneous** | All elements must be of the **same data type** (all ints, all floats, etc.) |
| **Contiguous memory** | Elements are stored in **continuous memory locations** |
| **Fixed size** | Size cannot be changed after creation (static) |
| **Fast operations** | Element-wise operations without explicit loops |
| **Less memory** | Takes less memory than lists (no type info per element) |

---

## 🔹 NumPy Array vs Python List – Key Differences

| Feature | NumPy Array | Python List |
|---------|-------------|--------------|
| **Data type** | Homogeneous (same type) | Heterogeneous (mixed types allowed) |
| **Memory** | Contiguous (continuous) | Non-contiguous (scattered) |
| **Memory usage** | Less (no type overhead per element) | More (stores type info per element) |
| **Speed** | Very fast (vectorized operations) | Slower (loops required) |
| **Size** | Fixed (cannot resize) | Dynamic (can resize) |
| **Operations** | Element-wise without loops | Loops needed for most operations |
| **Part of** | NumPy library (external) | Python core (built-in) |

---

## 🔹 Why Contiguous Memory Makes Arrays Faster

### In NumPy Array (Contiguous):
```
Memory:  [100] [101] [102] [103] [104]
         | 10 | 20 | 30 | 40 | 50 |
```
- Every element takes fixed size (e.g., 1 byte for int)
- Next element is at next memory location
- Direct access using index: `array[3]` → directly go to location `100 + 3`

### In Python List (Non-contiguous):
```
Memory:  [100] -> [150] -> [130] -> [200] -> [180]
         | 10 |    | 20 |    | 30 |    | 40 |    | 50 |
```
- Elements are scattered
- Each element stores a **reference** to the next element
- Slower access due to following pointers

> ⚠️ **Interview Tip:** Searching is **faster in arrays** (direct index access). Insertion/deletion is **easier in lists** (no memory gaps to fill).

---

## 🔹 Vectorized Operations – The Real Power 💪

> In NumPy, operations are applied to **all elements at once** (element-wise), without writing explicit loops.

### Example:
```python
import numpy as np

arr = np.array([1, 2, 3, 4, 5])
result = arr * 3   # Multiplies EVERY element by 3
print(result)      # Output: [3, 6, 9, 12, 15]
```

✅ No `for` loop needed – much faster for large datasets.

---

## 🔹 NumPy Arrays Use Less Memory

| Reason | Explanation |
|--------|-------------|
| Same data type | No need to store type info for each element |
| Contiguous | No pointer/reference overhead |
| Static size | No extra space for future growth |

> Example: Array of 1000 integers takes significantly **less memory** than list of 1000 integers.

---

## 🔹 When to Use Array vs List

| Scenario | Recommended |
|----------|-------------|
| Size is known in advance | ✅ NumPy Array |
| Size may change (grow/shrink) | ✅ Python List |
| Need very fast mathematical operations | ✅ NumPy Array |
| Mixed data types (numbers + strings) | ✅ Python List |
| Working with large datasets (ML, DS) | ✅ NumPy Array |
| Simple scripting, small data | ✅ Python List |

---

## 📊 Quick Reference Table

| Feature | NumPy Array | Python List |
|---------|-------------|--------------|
| Homogeneous | ✅ Yes | ❌ No |
| Contiguous memory | ✅ Yes | ❌ No |
| Resizable | ❌ No | ✅ Yes |
| Vectorized operations | ✅ Yes | ❌ No (needs loops) |
| Memory efficient | ✅ Yes | ❌ No |
| Part of core Python | ❌ No (needs import) | ✅ Yes |
| Best for | Numerical computing | General purpose |

---

## ✅ Important Points for Exams/Interviews

1. **NumPy stands for Numerical Python.**
2. **Arrays are homogeneous** – all elements same data type.
3. **Arrays use contiguous memory** – faster access.
4. **Lists are heterogeneous** – can mix data types.
5. **Lists use non-contiguous memory** – slower but flexible.
6. **Arrays cannot be resized** (static), lists can (dynamic).
7. **Vectorized operations** – apply operation to entire array without loops.
8. **Arrays take less memory** than lists for same number of elements.
9. **Insertion/deletion is easier in lists** than arrays.
10. **Searching is faster in arrays** than lists (direct index access).

---

## 🧪 Quick Example (Try Yourself)

```python
import numpy as np

# Creating a NumPy array
arr = np.array([10, 20, 30, 40, 50])

# Accessing elements
print(arr[0])     # 10
print(arr[-1])    # 50

# Vectorized operation (no loop!)
print(arr * 2)    # [20, 40, 60, 80, 100]

# Check memory usage
print(arr.nbytes) # Number of bytes used

# Compare with list
my_list = [10, 20, 30, 40, 50]
print(arr[0])     # 10 (same)
```

---

## 🎯 Final Pro Tips

| You want to... | Use this |
|----------------|----------|
| Fast math on large data | NumPy array |
| Mixed data types | Python list |
| Fixed size, known upfront | NumPy array |
| Dynamic size (add/remove) | Python list |
| Machine learning / Data science | NumPy array |
| Simple everyday scripting | Python list |

---

## 🚀 Summary

> **NumPy arrays** = Fast, memory-efficient, homogeneous, contiguous memory  
> **Python lists** = Flexible, heterogeneous, dynamic, but slower  
> **Key difference** = Homogeneity + Contiguous memory vs Heterogeneity + Dynamic  

```python
# Visual difference
numpy_array = np.array([1, 2, 3, 4])   # All ints, continuous memory
python_list = [1, "hello", 3.5, True]  # Mixed types, scattered memory
```

---

Happy Coding! 🐍📊  
You are now ready to answer any NumPy vs List question in exams and interviews. 💪
