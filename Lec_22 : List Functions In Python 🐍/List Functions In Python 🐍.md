# 📚 Python List Built-in Functions
<sub>📺 <a href="https://youtu.be/cS_4YJx5KvU?si=BL1j6qOzfIzQ_kjQ">Video Link</a></sub>
## 🔹 What are Built-in List Functions?

> Built-in list functions (also called **methods**) are pre-defined functions that help you **manipulate, search, modify, and get information** about lists.

✅ You can use them directly – no need to write from scratch.

---

## 1. `len()` – Length of List 📏

Returns the total number of elements in a list.

```python
list1 = [10, 20, 30, 40, 50]
print(len(list1))   # Output: 5
```

---

## 2. `list()` – Create a List from Other Data 🏗️

Converts other data types (like string, tuple) into a list.

```python
print(list("hello"))   # Output: ['h', 'e', 'l', 'l', 'o']
print(list((1,2,3)))   # Output: [1, 2, 3]
```

---

## 3. `append()` – Add Single Element at End ➕

Adds **one element** at the end of the list.

```python
list1 = [1, 2, 3]
list1.append(4)
print(list1)   # Output: [1, 2, 3, 4]

# Can also append another list as a single element
list1.append([5,6])
print(list1)   # Output: [1, 2, 3, 4, [5,6]]
```

> ⚠️ `append()` adds **one item** – even if that item is a list.

---

## 4. `extend()` – Add Multiple Elements 🔗

Adds **each element** of another list (or iterable) to the end.

```python
list1 = [1, 2, 3]
list1.extend([4, 5, 6])
print(list1)   # Output: [1, 2, 3, 4, 5, 6]
```

| Method | Adds as |
|--------|---------|
| `append([4,5])` | Single nested list `[4,5]` |
| `extend([4,5])` | Individual elements `4, 5` |

> ✅ `extend()` is faster for adding multiple items.

---

## 5. `insert()` – Add Element at Specific Position 📍

Inserts an element at a given index. Shifts other elements to the right.

```python
list1 = [10, 20, 30, 40]
list1.insert(2, 25)   # Insert 25 at index 2
print(list1)          # Output: [10, 20, 25, 30, 40]
```

**Syntax:** `list.insert(index, element)`

---

## 6. `count()` – Count Occurrences 🔢

Returns the number of times an element appears in the list.

```python
list1 = [10, 20, 10, 30, 10, 40]
print(list1.count(10))   # Output: 3
print(list1.count(99))   # Output: 0
```

---

## 7. `index()` – Find Position of First Occurrence 🔍

Returns the **index** of the **first** occurrence of an element.

```python
list1 = [10, 20, 30, 20, 40]
print(list1.index(20))   # Output: 1 (first 20 at index 1)
```

If element not found → `ValueError`

```python
# print(list1.index(99))   # ❌ ValueError
```

---

## 8. `remove()` – Remove First Occurrence 🗑️

Removes the **first occurrence** of a specific value.

```python
list1 = [10, 20, 30, 20, 40]
list1.remove(20)        # Removes first 20
print(list1)            # Output: [10, 30, 20, 40]
```

If element not found → `ValueError`

---

## 9. `pop()` – Remove by Index (and Return) 📤

Removes and **returns** the element at a given index.

```python
list1 = [10, 20, 30, 40]
removed = list1.pop(2)   # Removes element at index 2 (30)
print(removed)           # Output: 30
print(list1)             # Output: [10, 20, 40]
```

### Without argument – removes last element:
```python
list1.pop()              # Removes last element (40)
print(list1)             # Output: [10, 20]
```

> 💡 `pop()` returns the removed element; `remove()` does not.

---

## 10. `sort()` – Sort in Place (Ascending by Default) ⬆️

Sorts the list **in ascending order** and modifies the original list.

```python
list1 = [5, 2, 8, 1, 9]
list1.sort()
print(list1)   # Output: [1, 2, 5, 8, 9]
```

### Descending order:
```python
list1.sort(reverse=True)
print(list1)   # Output: [9, 8, 5, 2, 1]
```

> ⚠️ `sort()` changes the original list (in-place).

---

## 11. `sorted()` – Return New Sorted List 🆕

Returns a **new sorted list** without modifying the original.

```python
original = [5, 2, 8, 1, 9]
new_list = sorted(original)
print(new_list)    # Output: [1, 2, 5, 8, 9]
print(original)    # Output: [5, 2, 8, 1, 9] (unchanged)
```

### Descending with `sorted()`:
```python
new_list = sorted(original, reverse=True)
print(new_list)    # Output: [9, 8, 5, 2, 1]
```

| Function | Modifies original? | Returns |
|----------|-------------------|---------|
| `list.sort()` | ✅ Yes (in-place) | `None` |
| `sorted(list)` | ❌ No | New list |

---

## 12. `reverse()` – Reverse List in Place 🔄

Reverses the order of the list (modifies original).

```python
list1 = [10, 20, 30, 40]
list1.reverse()
print(list1)   # Output: [40, 30, 20, 10]
```

> 💡 To reverse without modifying: use slicing `list1[::-1]`

---

## 13. `min()` – Minimum Value 📉

Returns the smallest element in the list.

```python
list1 = [5, 2, 8, 1, 9]
print(min(list1))   # Output: 1
```

---

## 14. `max()` – Maximum Value 📈

Returns the largest element in the list.

```python
list1 = [5, 2, 8, 1, 9]
print(max(list1))   # Output: 9
```

---

## 15. `sum()` – Sum of All Elements ➕

Returns the sum of all numeric elements.

```python
list1 = [10, 20, 30]
print(sum(list1))   # Output: 60
```

> ⚠️ Works only for numeric lists.

---

## 📊 Complete Quick Reference Table

| Function | What it does | Example | Output |
|----------|--------------|---------|--------|
| `len(list)` | Number of elements | `len([1,2,3])` | 3 |
| `list(iterable)` | Convert to list | `list("abc")` | `['a','b','c']` |
| `append(x)` | Add x at end | `[1].append(2)` | `[1,2]` |
| `extend([x,y])` | Add multiple | `[1].extend([2,3])` | `[1,2,3]` |
| `insert(i,x)` | Insert at index i | `[1,3].insert(1,2)` | `[1,2,3]` |
| `count(x)` | Count occurrences | `[1,1,2].count(1)` | 2 |
| `index(x)` | First index of x | `[10,20].index(20)` | 1 |
| `remove(x)` | Remove first x | `[1,2,1].remove(1)` | `[2,1]` |
| `pop(i)` | Remove & return at i | `[10,20].pop(0)` | `10` |
| `sort()` | Sort ascending (in-place) | `[3,1,2].sort()` | `[1,2,3]` |
| `sorted(list)` | Return new sorted list | `sorted([3,1,2])` | `[1,2,3]` |
| `reverse()` | Reverse in-place | `[1,2,3].reverse()` | `[3,2,1]` |
| `min(list)` | Smallest element | `min([5,1,9])` | 1 |
| `max(list)` | Largest element | `max([5,1,9])` | 9 |
| `sum(list)` | Sum of elements | `sum([1,2,3])` | 6 |

---

## ✅ Important Points for Exams/Interviews

1. **`append()` vs `extend()`** – append adds 1 item, extend adds multiple items.
2. **`sort()` vs `sorted()`** – sort modifies original, sorted returns new list.
3. **`remove()` vs `pop()`** – remove by value, pop by index (and returns value).
4. **`pop()` without index** – removes last element.
5. **`count()`** returns 0 if element not found (no error).
6. **`index()`** gives error if element not found.
7. **`reverse()`** modifies original list.
8. **`min()`, `max()`, `sum()`** work on numeric lists.

---

## 🧪 Practice Examples (Try Yourself)

```python
my_list = [5, 3, 8, 3, 2, 8, 1]

print(len(my_list))           # ?
print(my_list.count(3))       # ?
print(my_list.index(8))       # ?
my_list.append(10)
print(my_list)                # ?
my_list.insert(2, 99)
print(my_list)                # ?
my_list.remove(3)
print(my_list)                # ?
print(my_list.pop(4))         # ?
my_list.sort()
print(my_list)                # ?
my_list.reverse()
print(my_list)                # ?
print(min(my_list))           # ?
print(max(my_list))           # ?
print(sum(my_list))           # ?
```

**Answers:**
- 7
- 2
- 2
- `[5,3,8,3,2,8,1,10]`
- `[5,3,99,8,3,2,8,1,10]`
- `[5,99,8,3,2,8,1,10]`
- `2` (removed element)
- `[1,3,5,8,8,10,99]` (after sort)
- `[99,10,8,8,5,3,1]` (after reverse)
- 1
- 99
- 134

---

## 🎯 Final Pro Tips

| You want to... | Use this |
|----------------|----------|
| Add one item | `append()` |
| Add many items | `extend()` |
| Add at specific position | `insert()` |
| Count occurrences | `count()` |
| Find position | `index()` |
| Remove by value | `remove()` |
| Remove by index | `pop()` |
| Sort (change original) | `sort()` |
| Sort (get new list) | `sorted()` |
| Reverse order | `reverse()` or `[::-1]` |
| Smallest value | `min()` |
| Largest value | `max()` |
| Total sum | `sum()` |

---

## 🚀 Summary

> **List methods = Manipulate + Search + Modify + Analyze**  
> - `append`, `extend`, `insert` → add elements  
> - `remove`, `pop` → delete elements  
> - `count`, `index` → search  
> - `sort`, `reverse` → reorder  
> - `min`, `max`, `sum`, `len` → analyze

---

Happy Coding! 🐍📋  
You are now ready to answer any list methods question in exams and interviews. 💪
