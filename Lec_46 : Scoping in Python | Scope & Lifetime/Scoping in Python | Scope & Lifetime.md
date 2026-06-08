# 🔍 Variable Scope and Lifetime in Python
<sub>📺 <a href="https://youtu.be/dPyalFo3YPw?si=wMl267payA2AXpD-">Video Link</a></sub>
## 🔹 What is Variable Scope?

> **Scope** refers to the **region or block of code** in a program where a variable is **recognized and accessible**.

✅ Think of scope as the "area of influence" of a variable – where it can be seen and used.

### Simple Analogy:
> In a movie, a character might be known in "Chor Bazaar" but not outside it. Similarly, a variable may be known inside a function but not outside.

---

## 🔹 Scope vs Lifetime – The Key Difference

| Concept | Definition | Question it answers |
|---------|------------|---------------------|
| **Scope** | Where can the variable be accessed? | "Where is the variable known?" |
| **Lifetime** | How long does the variable exist in memory? | "How long does the variable live?" |

> 🔥 **Important:** Scope is about **accessibility** (where you can use it).  
> Lifetime is about **existence** (how long it stays in memory).

---

## 🔹 Two Types of Scope

| Type | Where declared | Where accessible | Lifetime |
|------|----------------|------------------|----------|
| **Local Variable** | Inside a function | Only inside that function | Until function returns |
| **Global Variable** | Outside any function (top of program) | Entire program (inside and outside functions) | Throughout program execution |

---

# 1. Local Variable

> A variable defined **inside a function** is called a **local variable**.  
> It is **only accessible within that function**.

### Example:

```python
def my_function():
    local_var = "I am local"   # Local variable
    print(local_var)           # ✅ Accessible inside function

my_function()
# print(local_var)  # ❌ Error! local_var is not accessible outside
```

### Characteristics of Local Variables:

| Property | Description |
|----------|-------------|
| **Scope** | Limited to the function only |
| **Lifetime** | Created when function is called, destroyed when function returns |
| **Access** | Cannot be accessed from outside the function |
| **Memory** | Stored temporarily in RAM during function execution |

---

# 2. Global Variable

> A variable defined **outside any function** (at the top level) is called a **global variable**.  
> It is accessible **everywhere** in the program – inside and outside functions.

### Example:

```python
global_var = "I am global"   # Global variable

def my_function():
    print(global_var)        # ✅ Accessible inside function

my_function()
print(global_var)            # ✅ Accessible outside function
```

### Characteristics of Global Variables:

| Property | Description |
|----------|-------------|
| **Scope** | Entire program (inside and outside all functions) |
| **Lifetime** | Created when program starts, destroyed when program ends |
| **Access** | Can be accessed from anywhere |
| **Memory** | Stays in memory throughout program execution |

---

## 🔹 Practical Example – Demonstrating Scope

```python
# Global variable (outside any function)
global_var = "I am GLOBAL - available everywhere"

def my_function():
    # Local variable (inside function)
    local_var = "I am LOCAL - available only inside this function"
    
    # Both are accessible INSIDE the function
    print(local_var)   # ✅ Works: local_var exists here
    print(global_var)  # ✅ Works: global_var is accessible anywhere

# Call the function
my_function()

# Accessing outside the function
print(global_var)      # ✅ Works: global_var exists throughout program

# Accessing local variable outside
print(local_var)       # ❌ NameError: local_var is not defined outside
```

### Output:

```
I am LOCAL - available only inside this function
I am GLOBAL - available everywhere
I am GLOBAL - available everywhere
NameError: name 'local_var' is not defined
```

---

## 🔹 What is Lifetime?

> **Lifetime** is the duration for which a variable **exists in memory**.

| Variable Type | When created | When destroyed |
|---------------|--------------|----------------|
| **Local Variable** | When function is called | When function returns |
| **Global Variable** | When program starts | When program ends |

### Visual Representation:

```
Program Start
    │
    ▼
Global Variable Created ──────────────────┐
    │                                      │
    │    Function Call                     │
    │        │                             │
    │        ▼                             │
    │    Local Variable Created            │
    │        │                             │
    │        ▼                             │
    │    Function executes                 │
    │        │                             │
    │        ▼                             │
    │    Local Variable Destroyed          │
    │                                      │
    ▼                                      ▼
Program Ends ──────────────────────── Global Variable Destroyed
```

---

## 🔹 Complete Code Example with Explanation

```python
# GLOBAL variable - exists throughout program
global_var = "I am global available"

def f1():
    # LOCAL variable - exists only inside this function
    local_var = "I am locally available"
    
    # Both are accessible INSIDE the function
    print(local_var)   # ✅ Local scope (inside function)
    print(global_var)  # ✅ Global scope (accessible anywhere)

# Call the function
f1()

# After function returns, local_var is destroyed
print(global_var)      # ✅ Still works (global exists)

# This will cause ERROR - local_var no longer exists
# print(local_var)     # ❌ NameError: name 'local_var' is not defined
```

### What happens step by step:

| Step | Action | Memory State |
|------|--------|--------------|
| 1 | `global_var` created | `global_var` in memory |
| 2 | `f1()` called | Control moves to function |
| 3 | `local_var` created | `local_var` + `global_var` in memory |
| 4 | `print(local_var)` works | Both accessible |
| 5 | `print(global_var)` works | Both accessible |
| 6 | Function returns | `local_var` destroyed |
| 7 | `print(global_var)` works | Only `global_var` remains |
| 8 | Program ends | `global_var` destroyed |

---

## 📊 Quick Reference Table

| Feature | Local Variable | Global Variable |
|---------|----------------|-----------------|
| **Declaration location** | Inside a function | Outside any function |
| **Scope (Where accessible)** | Only inside that function | Entire program |
| **Lifetime (How long it exists)** | From function call to return | Entire program execution |
| **Access inside function** | ✅ Yes (its own function) | ✅ Yes (anywhere) |
| **Access outside function** | ❌ No | ✅ Yes |
| **Memory** | Temporary (stack) | Permanent (global memory) |

---

## ✅ Important Points for Exams/Interviews

1. **Scope** = Where a variable can be **accessed** (region of code).
2. **Lifetime** = How long a variable **exists in memory** (duration).
3. **Local variables** are defined **inside functions** – scope is limited to that function.
4. **Global variables** are defined **outside functions** – scope is the entire program.
5. Local variables are **created when function is called** and **destroyed when function returns**.
6. Global variables exist for the **entire program execution**.
7. A local variable **cannot be accessed outside its function** (NameError).
8. A global variable **can be accessed both inside and outside functions**.

---

## 🧪 Practice Examples (Try Yourself)

```python
# Example 1: Identify scope
x = 10   # Global or Local?

def test():
    y = 20   # Global or Local?
    print(x)   # Will this work?
    print(y)   # Will this work?

test()
print(x)   # Will this work?
print(y)   # Will this work?
```

**Answers:**
- `x` = Global variable
- `y` = Local variable
- `print(x)` inside function → ✅ Works (global accessible)
- `print(y)` inside function → ✅ Works (local accessible)
- `print(x)` outside function → ✅ Works (global accessible)
- `print(y)` outside function → ❌ NameError (local not accessible outside)

---

## 🎯 Final Pro Tips

| You want to... | Use this |
|----------------|----------|
| Create variable accessible only inside a function | Local variable |
| Create variable accessible everywhere in program | Global variable |
| Know where a variable can be used | Check its **Scope** |
| Know how long a variable exists | Check its **Lifetime** |

---

## 🚀 Summary

> **Scope** = "Where is the variable known?" (accessibility)  
> **Lifetime** = "How long does the variable live?" (existence in memory)

```python
# Quick visual
global_var = "Known everywhere, lives entire program"  # Global

def my_func():
    local_var = "Known only here, lives only during function call"  # Local
    print(global_var)  # ✅ Works
    print(local_var)   # ✅ Works

my_func()
print(global_var)      # ✅ Works
# print(local_var)     # ❌ NameError - local_var destroyed after function returns
```

---

Happy Coding! 🐍🔍  
You are now ready to answer any question on variable scope and lifetime in Python. 💪
