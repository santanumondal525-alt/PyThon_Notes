# 🧩 Functions in Python
<sub>📺 <a href="https://youtu.be/jpqi_HRdpGA?si=JdSwSIhAf58BbRhs">Video Link</a></sub>
## 🔹 What is a Function?

> A **function** is a **reusable block of code** that performs a specific task. It helps organize code into **logical, modular blocks**.

✅ Functions are fundamental to **modular programming** – breaking a program into smaller, manageable pieces.

---

## 🔹 Why Use Functions? – Advantages

| Advantage | Explanation |
|-----------|-------------|
| **Reusability** | Write once, use many times. Call the function whenever needed. |
| **Modularity** | Break complex programs into smaller, simpler functions. |
| **Easy Debugging** | Test and fix each function independently. |
| **Abstraction** | Hide complex implementation details. |
| **Code Organization** | Cleaner, more readable, and maintainable code. |
| **Reduces Code Duplication** | No need to write the same code again and again. |

---

## 🔹 Function Syntax in Python

```python
def function_name(parameters):
    """Docstring (optional) - explains what the function does"""
    # Function body (code)
    # ...
    return value   # Optional
```

### Syntax Breakdown:

| Part | Required? | Description |
|------|-----------|-------------|
| `def` | ✅ Mandatory | Keyword to define a function |
| `function_name` | ✅ Mandatory | Name of the function (follow naming rules) |
| `(parameters)` | ❌ Optional | Input values passed to the function |
| `:` colon | ✅ Mandatory | Marks the end of the function header |
| Docstring | ❌ Optional | Triple-quoted string describing the function |
| Function body | ✅ Mandatory | Indented code that does the work |
| `return` | ❌ Optional | Returns a value to the caller |

> 💡 **Indentation is critical!** The function body must be indented (usually 4 spaces).

---

## 🔹 Example 1: Simple Function (No Parameters, No Return)

```python
def f1():
    """This function prints Hello"""
    print("Hello")

# Calling the function
f1()
```

**Output:** `Hello`

> 💡 Function defined with `def`, called by writing its name with parentheses `()`.

---

## 🔹 Example 2: Function with Parameter (No Return)

```python
def f2(name):
    """This function prints the name passed to it"""
    print(name)

# Calling the function with an argument
f2("Varun")
```

**Output:** `Varun`

### How it works:
1. `f2("Varun")` is called – `"Varun"` is passed as an **argument**.
2. The parameter `name` receives the value `"Varun"`.
3. `print(name)` prints `"Varun"`.

> 💡 **Parameter** = variable in function definition  
> **Argument** = actual value passed when calling the function

---

## 🔹 Example 3: Function with Parameter and Return Value

```python
def square(x):
    """This function takes a number and returns its square"""
    return x ** 2

# Get user input
num = int(input("Enter a number: "))
result = square(num)
print(result)
```

**Input:** `10`  
**Output:** `100`

### Execution Flow:

| Step | Action |
|------|--------|
| 1 | User enters `10` → stored in `num` |
| 2 | `square(num)` is called → `10` passed to `x` |
| 3 | `x ** 2` = `10 * 10` = `100` |
| 4 | `return 100` sends value back |
| 5 | `100` is stored in `result` |
| 6 | `print(result)` → `100` |

> ✅ `return` sends a value back to where the function was called.

---

## 🔹 Function with Docstring

A **docstring** is a string literal that appears as the first statement in a function. It documents what the function does.

```python
def add(a, b):
    """This function returns the sum of two numbers"""
    return a + b

print(add(5, 3))   # Output: 8

# View docstring
print(add.__doc__)   # Output: This function returns the sum of two numbers
```

> 💡 Docstrings are **optional** but highly recommended for code clarity.

---

## 🔹 Parameters vs Arguments

| Term | Definition | Example |
|------|------------|---------|
| **Parameter** | Variable in function definition | `def square(x):` → `x` is parameter |
| **Argument** | Actual value passed when calling | `square(10)` → `10` is argument |

---

## 🔹 The `return` Statement

| Point | Explanation |
|-------|-------------|
| `return` sends a value back to the caller | `return x + y` |
| Without `return`, function returns `None` | `def f(): print("Hi")` → returns `None` |
| `return` can also exit a function early | `if condition: return` |
| A function can have multiple return statements | Different conditions return different values |

> ⚠️ **Important:** A function does NOT have to have a `return` statement. If omitted, it returns `None`.

---

## 🔹 Function Calling – How Control Flows

```
Program Start
    │
    ▼
Call f2("Varun")
    │
    ▼
Control jumps to function definition
    │
    ▼
Execute function body (print name)
    │
    ▼
Return to where function was called
    │
    ▼
Continue with next statement
```

---

## 📊 Complete Reference Table

| Component | Required? | Example |
|-----------|-----------|---------|
| `def` keyword | ✅ Yes | `def my_func():` |
| Function name | ✅ Yes | `calculate_square` |
| Parentheses `()` | ✅ Yes | `()` |
| Parameters | ❌ No | `(x, y)` |
| Colon `:` | ✅ Yes | `:` |
| Docstring | ❌ No | `"""Returns square"""` |
| Indented body | ✅ Yes | `return x * x` |
| `return` | ❌ No | `return result` |

---

## ✅ Important Points for Exams/Interviews

1. **`def`** keyword is mandatory to define a function.
2. **Function name** should be meaningful and follow naming conventions (lowercase with underscores).
3. **Parentheses** `()` are mandatory even if there are no parameters.
4. **Colon** `:` ends the function header.
5. **Indentation** defines the function body – no curly braces `{}`.
6. **Parameters** are optional – a function can have 0, 1, or multiple parameters.
7. **`return`** is optional – without it, the function returns `None`.
8. **Docstrings** are optional but good practice for documentation.
9. **Calling** a function: `function_name(arguments)`
10. Functions promote **reusability** and **modularity**.

---

## 🧪 Practice Examples (Try Yourself)

```python
# 1. Function with no parameters, no return
def greet():
    print("Good Morning!")

greet()

# 2. Function with one parameter, no return
def wish(name):
    print(f"Hello {name}!")

wish("Priya")

# 3. Function with two parameters and return
def multiply(a, b):
    """Returns product of two numbers"""
    return a * b

result = multiply(4, 5)
print(result)

# 4. Function with default parameter
def power(base, exp=2):
    return base ** exp

print(power(5))      # 25 (uses default exp=2)
print(power(2, 3))   # 8 (overrides default)

# 5. Function returning multiple values
def get_min_max(numbers):
    return min(numbers), max(numbers)

minimum, maximum = get_min_max([5, 2, 8, 1, 9])
print(minimum, maximum)   # 1 9
```

---

## 🎯 Final Pro Tips

| You want to... | Use this |
|----------------|----------|
| Create a function | `def function_name():` |
| Pass data to function | Add parameters: `def func(param):` |
| Get data back from function | Use `return` statement |
| Describe what function does | Add a docstring `"""description"""` |
| Call a function | `function_name(arguments)` |
| Make a parameter optional | Give it a default value: `def func(x=10):` |

---

## 🚀 Summary

> **Function = Reusable block of code**
> - **`def`** → define a function
> - **Parameters** → input values (optional)
> - **`return`** → output value (optional)
> - **Docstring** → documentation (optional)
> - **Indentation** → defines function body
> - **Call** → use function by name with parentheses

```python
# Quick visual
def add(a, b):
    """Returns sum of two numbers"""
    return a + b

result = add(5, 3)   # Calling the function
print(result)        # 8
```

---

Happy Coding! 🐍🧩  
You are now ready to answer any question on Python functions in exams and interviews. 💪
