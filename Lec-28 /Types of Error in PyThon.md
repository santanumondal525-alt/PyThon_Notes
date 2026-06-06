# 🍃 Types of Error in PyThon

<sub>📺 <a href="https://youtu.be/aPNQdMmyQKA?si=1GJ0coZ_quWfP1wQ">Video Link</a></sub>

Errors are a natural part of coding in any language. They are valuable because they teach you how to code correctly. In Python, errors are broadly categorized into three main types.

1. **🚫 Syntax Errors**
2. **⏱️ Runtime Errors (or Exceptions)**
3. **🧠 Logical Errors**

---

### 1. 🚫 Syntax Errors
These occur when you violate the grammar rules of Python. The code cannot even run; the interpreter points out the error before execution. Think of it like a spelling or grammar mistake.

- **📝 Definition:** An error in the structure or rules of the language.
  
- **⚠️ Common Examples:**
    - **Missing Colon (`:`)** ✍️: Forgetting the colon at the end of `if`, `else`, `while`, `for` statements.
    - **Missing/Unmatched Parentheses (`()`) 🧩:** Opening a bracket but forgetting to close it.
    - **Missing Quotes (`' '` or `" "`) 💬:** Forgetting to put a string inside quotes.
    - **Using Keywords as Variable Names 🔑:** Trying to name a variable `True`, `False`, or `None`, which are reserved words.
    - **Incorrect Indentation ➡️:** Not putting proper spaces to define a code block (like inside an `if` statement).

---

### 2. ⏱️ Runtime Errors (or Exceptions)
These errors occur while the program is running. The grammar is perfect, but during execution, an operation is impossible.

- **📝 Definition:** An error that crashes a running program, even with correct syntax.
- **💥 Common Examples:**
    - **Name Error 🏷️:** Using a variable that hasn't been defined yet.
        ```python
        a = 20
        print(b) # NameError: name 'b' is not defined ❌
        ```
    - **Type Error 🧱:** Mixing incompatible data types in an operation.
        ```python
        x = "20" # String 📝
        y = 10   # Integer 🔢
        print(x / y) # TypeError: can't divide string by int ❌
        ```
    - **Index Error 🔢:** Looking for a position in a list that doesn't exist.
        ```python
        list1 = [10, 20, 30]
        # Indexes: 0️⃣, 1️⃣, 2️⃣
        print(list1[4]) # IndexError: list index out of range ❌
        ```
    - **Division by Zero Error ➗0️⃣:** Trying to divide a number by zero (mathematically impossible).
    - **Attribute Error 🛠️:** Calling a method that an object doesn't have.
        ```python
        s = "Hello"
        s.reverse() # AttributeError: strings don't have reverse() ❌
        ```

---

### 3. 🧠 Logical Errors
These are the sneaky errors. The code runs perfectly without crashing and gives an output, but the output is **wrong** because the logic or algorithm is flawed.

- **📝 Definition:** An error that produces an incorrect result while the program runs successfully.
- **🤔 Common Examples:**
    - **Wrong Operator Precedence 🧮:** Forgetting the math order (BODMAS/PEMDAS).
        ```python
        a = 5
        b = 10
        average = a + b / 2 
        # Wrong Result: 10.0 (5 + 5.0) 😱
        # Correct Logic: average = (a + b) / 2  → 7.5 ✅
        ```
    - **Infinite Loop 🔁:** A loop whose exit condition is never met.
        ```python
        x = 0
        while x < 20:
            print(x)
            # Forgot x += 1 😵 -> Prints '0' forever!
        ```
    - **Misunderstanding Requirements 🎯:** Coding the wrong algorithm for the problem.

---

### 📊 Quick Revision Table

| Error Type | When? | Does Program Run? | Emoji Hint | Key Characteristic |
| :--- | :--- | :--- | :--- | :--- |
| **Syntax** | Before Execution | ❌ No | 🚫 | Violates grammar (missing `:`, `" "`). |
| **Runtime** | During Execution | ⚠️ Starts, then Crashes | ⏱️ | Syntax OK, but operation fails (wrong type). |
| **Logical** | During Execution | ✅ Yes, fully | 🧠 | Runs, but produces an incorrect output. |
