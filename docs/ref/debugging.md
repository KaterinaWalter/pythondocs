---
layout: default
title: "🐞 Debugging Errors" 
parent: References
nav_order: 2
---

# 🐞 Debugging Errors
{:.no_toc}

### 🐍 Python Debugging Process

{: .highlight } 
Code not working? Follow the steps in the **debugging process** below _before_ asking a peer or your teacher! Fixing your own errors, no matter how small, is one of the _best_ ways to become a better coder. 

1. **Read the Error Message**

   * Look at the **bottom line** of the traceback — that's the actual error type (e.g., `NameError`, `IndentationError`, `TypeError`).
   * Read the **line number** the error happened on and the line **above it**, too.

2. **Check Your Spacing and Indentation**

   * Make sure every **indent is exactly 4 spaces**, not tabs.
   * Blocks like `if`, `for`, `while`, `def`, and `class` must be followed by a colon (`:`) and indented on the next line.
   * Every nested block should line up vertically.

3. **Check Your Capitalization**

   * Python is **case-sensitive**. `print`, `Print`, and `PRINT` are all different!
   * Be consistent with how you spell variable names, functions, and keywords.

4. **Check Spelling and Naming**

   * Misspelled variable? Function name? Python won’t guess — you must match exactly.
   * Watch for typos like `pritn` instead of `print`.

5. **Check Symbols and Syntax**

   * Strings must be inside quotes: `"Hello"` or `'Hi'`
   * Use `==` for comparison, not `=`
   * Colons (`:`) after `if`, `for`, `while`, `def`, and `class`
   * Matching parentheses `()`, brackets `[]`, and braces `{}`

6. **Print Often**

   * Add `print()` statements to check what your variables contain.
   * Print just before the line that crashes to see what’s going on.

7. **Run Small Pieces at a Time**

   * Don’t write 50 lines and then run. Test **after every few lines**.
   * Break big problems into small chunks and test each one.

8. **Use Meaningful Variable Names**

   * This makes it easier to track your logic and avoid confusion.

9. **Ask Yourself Questions**

   * What is this line trying to do?
   * What _type_ is this variable? (`int`, `str`, `list`…)
   * Should this function _return_ something? Is it?

10. **If All Else Fails…**

    * Comment out parts of your code and slowly re-enable them.
    * Use an online tool like PythonTutor.com to step through code.


