# 🐍 Types of Errors in Python

## 📖 Introduction

Errors are a normal and important part of programming.

Whenever we write code, errors are likely to occur. These errors help us learn how to write better and more efficient programs. In fact, debugging errors is one of the best ways to improve programming skills.

In Python, errors are mainly classified into three categories:

1. **Syntax Errors**
2. **Runtime Errors**
3. **Logical Errors**

---

# 1️⃣ Syntax Errors

## 📌 Definition

A Syntax Error occurs when the rules (syntax) of Python are violated.

Python cannot understand the code and stops execution before running the program.

### Common Causes

- Missing colon (`:`)
- Unmatched parentheses
- Missing quotes in strings
- Using Python keywords as variable names
- Incorrect indentation

---

## Example 1: Missing Colon

### ❌ Incorrect Code

```python
if x > 0
    print("Positive")
```

### Error

```python
SyntaxError
```

### ✅ Correct Code

```python
if x > 0:
    print("Positive")
```

---

## Example 2: Missing Quotes

### ❌ Incorrect Code

```python
print("Hello)
```

### Error

```python
SyntaxError
```

### ✅ Correct Code

```python
print("Hello")
```

---

## Example 3: Indentation Error

### ❌ Incorrect Code

```python
if x > 0:
print("Positive")
```

### Error

```python
IndentationError
```

### ✅ Correct Code

```python
if x > 0:
    print("Positive")
```

---

# 2️⃣ Runtime Errors

## 📌 Definition

A Runtime Error occurs when:

- The program is syntactically correct.
- The error occurs while the program is running.

The code starts execution but crashes during runtime.

---

## Common Runtime Errors

| Error Type | Description |
|------------|-------------|
| NameError | Variable not defined |
| TypeError | Invalid operation on data types |
| IndexError | Invalid index access |
| ZeroDivisionError | Division by zero |
| AttributeError | Invalid method or attribute |

---

## Example 1: Index Error

### Code

```python
list1 = [10, 20, 30]

print(list1[4])
```

### Why?

The valid indexes are:

| Value | Index |
|--------|--------|
| 10 | 0 |
| 20 | 1 |
| 30 | 2 |

Index `4` does not exist.

### Error

```python
IndexError
```

---

## Example 2: Name Error

### Code

```python
a = 20

print(b)
```

### Error

```python
NameError
```

### Why?

Variable `b` was never defined.

---

## Example 3: Division by Zero

### Code

```python
x = 10
y = 0

print(x / y)
```

### Error

```python
ZeroDivisionError
```

---

## Example 4: Type Error

### Code

```python
x = "20"
y = 10

print(x / y)
```

### Error

```python
TypeError
```

### Why?

A string cannot be divided by an integer.

---

## Example 5: Attribute Error

### Code

```python
string = "Hello"

string.reverse()
```

### Error

```python
AttributeError
```

### Why?

Strings do not have a `reverse()` method.

### ✅ Correct Way

```python
string = "Hello"

print(string[::-1])
```

### Output

```python
olleH
```

---

# 3️⃣ Logical Errors

## 📌 Definition

A Logical Error occurs when:

- The program executes successfully.
- No syntax error occurs.
- No runtime error occurs.
- The output is incorrect.

The mistake is in the logic of the program.

---

## Example 1: Wrong Average Calculation

### ❌ Incorrect Code

```python
a = 5
b = 10

average = a + b / 2

print(average)
```

### Step-by-Step Calculation

Python follows operator precedence.

First:

```python
10 / 2 = 5
```

Then:

```python
5 + 5 = 10
```

### Output

```python
10
```

### Problem

The correct average should be:

```python
(5 + 10) / 2 = 7.5
```

### ✅ Correct Code

```python
average = (a + b) / 2
```

### Correct Output

```python
7.5
```

---

## Example 2: Infinite Loop

### ❌ Incorrect Code

```python
x = 0

while x < 20:
    print(x)
```

### Problem

The value of `x` is never increased.

Therefore:

```python
x < 20
```

always remains `True`.

The loop runs forever.

This is called an **Infinite Loop**.

---

### ✅ Correct Code

```python
x = 0

while x < 20:
    print(x)
    x += 1
```

---

# 📊 Summary Table

| Error Type | When It Occurs | Program Executes? | Example |
|------------|---------------|-------------------|----------|
| Syntax Error | Python rules are violated | ❌ No | Missing `:` |
| Runtime Error | Error during execution | ⚠️ Partially | Division by zero |
| Logical Error | Wrong logic | ✅ Yes | Incorrect average formula |

---

# 🎯 Important Interview Questions

## Syntax Error

- Detected before execution
- Related to Python grammar rules

## Runtime Error

- Occurs during execution
- Program crashes while running

## Logical Error

- Program runs successfully
- Produces incorrect output
- Often the most difficult type of error to identify

---

# 🧠 Quick Revision

| Error | Example |
|---------|---------|
| SyntaxError | Missing colon |
| IndentationError | Wrong indentation |
| NameError | Undefined variable |
| TypeError | Wrong data type operation |
| IndexError | Invalid index |
| ZeroDivisionError | Division by zero |
| AttributeError | Invalid method |
| Logical Error | Wrong logic/formula |

---

# ✅ Final Conclusion

Python errors are mainly divided into three categories:

1. **Syntax Errors** → Errors in Python grammar.
2. **Runtime Errors** → Errors that occur during execution.
3. **Logical Errors** → Program runs but produces incorrect results.

Errors are not obstacles; they are valuable learning opportunities that help programmers improve their coding and debugging skills.
