# 🔧 Python List Operations
<sub>📺 <a href="https://youtu.be/C_XRxLPGbUw?si=m9-LjNTH2qE1KcpE">Video Link</a></sub>

## 🔹 Four Major Operations on Lists

|  | Operation | Meaning | Operator |
|---|-----------|---------|----------|
| 1 | **Concatenation** | Joining two lists | `+` |
| 2 | **Repetition** | Repeating a list multiple times | `*` |
| 3 | **Membership** | Checking if an item exists in a list | `in` / `not in` |
| 4 | **Slicing** | Extracting a portion of a list | `[start:stop:step]` |

---

### 1. Concatenation – Joining Lists ➕

Combines two or more lists into one.

```python
list1 = [1, 3, 5, 7]
list2 = [2, 4, 6, 8]
result = list1 + list2
print(result)   # Output: [1, 3, 5, 7, 2, 4, 6, 8]
```

> ⚠️ **Cannot use `+` between list and non-list** (e.g., list + number → error)

---

### 2. Repetition – Repeating Lists 🔁

Repeats a list a specified number of times using `*` operator.

```python
list1 = [1, 2, 5]
result = list1 * 3
print(result)   # Output: [1, 2, 5, 1, 2, 5, 1, 2, 5]
```

> ✅ Great for creating repeated patterns or initializing lists.

---

### 3. Membership – Check Item Existence ✅

Checks whether an item is present in a list.

| Operator | Meaning |
|----------|---------|
| `in` | Returns `True` if item exists |
| `not in` | Returns `True` if item does NOT exist |

```python
fruits = ["apple", "mango", "banana"]
print("mango" in fruits)      # True
print("grapes" in fruits)     # False
print("grapes" not in fruits) # True
```

---

### 4. Slicing – Extracting Parts of a List ✂️

## Syntax:
```python
list[start : stop : step]
```

| Parameter | Meaning | Default |
|-----------|---------|---------|
| `start` | Index to begin (included) | 0 |
| `stop` | Index to stop (**excluded**) | end of list |
| `step` | Jump size (1 = every element) | 1 |

> 🔥 **Most Important Rule:** `stop` index is **always excluded**.

---

## 🔹 Slicing Examples (Positive Indexing)

Let `my_list = [10, 20, 30, 40, 50, 60]`

| Slice | Meaning | Output |
|-------|---------|--------|
| `my_list[1:4]` | Index 1,2,3 | `[20, 30, 40]` |
| `my_list[:4]` | Start 0 to index 3 | `[10, 20, 30, 40]` |
| `my_list[2:]` | Index 2 to end | `[30, 40, 50, 60]` |
| `my_list[:]` | Entire list | `[10, 20, 30, 40, 50, 60]` |

---

## 🔹 Slicing with Step (Jump)

```python
my_list = [10, 20, 30, 40, 50, 60]
print(my_list[1:5:2])   # Start=1, Stop=5 (excluded), Step=2
```

**Step-by-step:**
- Index 1 → `20`
- Jump 2 → Index 3 → `40`
- Jump 2 → Index 5 (stop, excluded)

**Output:** `[20, 40]`

---

## 🔹 Negative Indexing in Slices

```python
my_list = [10, 20, 30, 40, 50, 60]
# Negative: -6  -5  -4  -3  -2  -1
```

| Slice | Meaning | Output |
|-------|---------|--------|
| `my_list[-4:-1]` | -4 to -2 (stop -1 excluded) | `[30, 40, 50]` |
| `my_list[-3:]` | -3 to end | `[40, 50, 60]` |
| `my_list[:-2]` | start to index -3 | `[10, 20, 30, 40]` |

> ✅ Negative stop index also **excluded**!

---

## 🔹 Reverse a List using Slicing 🔄

```python
my_list = [10, 20, 30, 40, 50, 60]
print(my_list[::-1])   # Output: [60, 50, 40, 30, 20, 10]
```

> 💡 `[::-1]` → start=end, step=-1 → traverses backwards

---

## 🔹 Special Slicing Cases

```python
my_list = [10, 20, 30, 40, 50, 60]
```

| Slice | Output | Explanation |
|-------|--------|-------------|
| `my_list[::2]` | `[10, 30, 50]` | Every 2nd element from start |
| `my_list[1::2]` | `[20, 40, 60]` | Every 2nd element from index 1 |
| `my_list[-2::-1]` | `[50, 40, 30, 20, 10]` | From 2nd last to beginning, reversed |
| `my_list[-2:-5:-1]` | `[50, 40, 30]` | Reverse slice from -2 to -4 |

---

## 📊 Complete Slicing Reference Table

| Task | Code (list = [10,20,30,40,50,60]) | Output |
|------|-------------------------------------|--------|
| First 3 elements | `list[:3]` | `[10,20,30]` |
| Last 3 elements | `list[-3:]` | `[40,50,60]` |
| Elements 2 to 5 | `list[1:5]` | `[20,30,40,50]` |
| Every 2nd element | `list[::2]` | `[10,30,50]` |
| Reverse list | `list[::-1]` | `[60,50,40,30,20,10]` |
| All except last 2 | `list[:-2]` | `[10,20,30,40]` |
| Last 2 reversed | `list[-2:][::-1]` or `list[:-3:-1]` | `[60,50]` |
| From index 3 to end | `list[3:]` | `[40,50,60]` |

---

## ✅ Important Points for Exams/Interviews

1. **Concatenation (`+`)** – joins lists, doesn't modify original.
2. **Repetition (`*`)** – repeats list, useful for initialization.
3. **Membership (`in` / `not in`)** – returns boolean.
4. **Slicing** does **NOT** modify original list – creates a new list.
5. **Stop index is always excluded** – most common mistake!
6. **Negative step (`[::-1]`)** reverses the list.
7. **Out of range slice** does not give error – returns whatever is available.

---

## 🧪 Practice Examples (Try Yourself)

```python
nums = [1, 2, 3, 4, 5, 6, 7, 8]

print(nums[2:6])        # ?
print(nums[:5])         # ?
print(nums[3:])         # ?
print(nums[::3])        # ?
print(nums[::-2])       # ?
print(nums[-5:-2])      # ?
print(5 in nums)        # ?
print([1,2] + [3,4])    # ?
print([1] * 4)          # ?
```

**Answers:**
- `[3, 4, 5, 6]`
- `[1, 2, 3, 4, 5]`
- `[4, 5, 6, 7, 8]`
- `[1, 4, 7]`
- `[8, 6, 4, 2]`
- `[4, 5, 6]`
- `True`
- `[1, 2, 3, 4]`
- `[1, 1, 1, 1]`

---

## 🎯 Final Pro Tips

| You want to... | Use this |
|----------------|----------|
| Join two lists | `list1 + list2` |
| Repeat a list | `list1 * n` |
| Check if item exists | `item in list` |
| Get first N items | `list[:N]` |
| Get last N items | `list[-N:]` |
| Get every 2nd item | `list[::2]` |
| Reverse a list | `list[::-1]` |
| Skip first and last | `list[1:-1]` |

---

## 🚀 Summary

> **List Operations = Concatenation (`+`) + Repetition (`*`) + Membership (`in`) + Slicing (`[start:stop:step]`)**  
> - Stop index is always excluded  
> - Negative step = reverse direction  
> - Slicing is very powerful for data extraction

---

Happy Coding! 🐍📋  
You are now ready to answer any list operation question in exams and interviews. 💪
