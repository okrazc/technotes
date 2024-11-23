ReST (reStructuredText) is a lightweight markup language commonly used for documentation in Python, especially in docstrings. It’s the format used by tools like Sphinx to generate Python documentation.

### **What Is ReST?**
- **ReST** is a plain-text markup syntax designed to be both human-readable and machine-readable.
- It allows you to format documentation with headings, lists, code blocks, links, and more.
- Python docstrings written in ReST style can be processed by tools like **Sphinx** to create HTML, PDF, or other documentation formats.

---

### **ReST Style Docstring Example**

Here’s an example of a function documented with ReST-style comments:

```python
def add_task(task):
    """
    Add a task to the task list.

    :param task: A string representing the task to be added.
    :type task: str
    :raises ValueError: If the task is empty or None.
    :return: The updated list of tasks.
    :rtype: list
    """
    if not task:
        raise ValueError("Task cannot be empty.")
    tasks.append(task)
    return tasks
```

---

### **Key Components of ReST Comments**

#### 1. **Short Description**
The first line is a concise summary of the function.

#### 2. **Detailed Description**
If needed, provide more detail in subsequent paragraphs.

#### 3. **Parameters (`:param`)**
- Use `:param` to describe each parameter.
- Optionally include the type with `:type`.

Example:
```python
:param task: A string representing the task to be added.
:type task: str
```

#### 4. **Return Value (`:return` and `:rtype`)**
- Use `:return` to describe the returned value.
- Use `:rtype` to specify the type of the return value.

Example:
```python
:return: The updated list of tasks.
:rtype: list
```

#### 5. **Exceptions (`:raises`)**
- Document exceptions that the function might raise.

Example:
```python
:raises ValueError: If the task is empty or None.
```

#### 6. **Example Usage**
You can include example usage, often with `code-block` directives:
```python
    Example:
    >>> add_task("Read a book")
    ['Read a book']
```

---

### **Advanced Features**

#### **Headings and Sections**
You can use headings to divide sections within the docstring.

```python
"""
Add a task to the task list.

Details
-------
This function appends a task to the global task list.
"""
```

#### **Lists**
You can use bullet or numbered lists:
```python
"""
Features:
- Adds a task to the list.
- Returns the updated list.

Steps:
1. Validate the input.
2. Append the task.
3. Return the updated list.
"""
```

#### **Code Blocks**
You can use `::` or `.. code-block::` for code examples:
```python
"""
Example::
    >>> add_task("Do laundry")
    ['Do laundry']
"""
```

---

### **Why Use ReST Style?**
1. **Tool Integration**: Tools like Sphinx can parse ReST and generate detailed, formatted documentation.
2. **Readability**: The syntax is clean and readable both as plain text and when rendered.
3. **Standardization**: Many Python projects use ReST for consistency in documentation.

---
Certainly! Let's go through a **hands-on example** of using **Sphinx** to generate documentation for a Python project. Along the way, I'll also demonstrate key **reStructuredText (ReST) features** used in docstrings.

---

### **Step 1: Install Sphinx**
First, install Sphinx using `pip`:
```bash
pip install sphinx
```

---

### **Step 2: Set Up a Sample Project**

Assume the following project structure:

```
project/
├── tasks.py               # Python file to document
└── docs/                  # Directory for Sphinx documentation
```

#### `tasks.py` (Example Code with ReST Docstrings):
```python
"""
Task Manager Module
===================

A module to manage a global task list. Provides functionality to
add, remove, list, and clear tasks.
"""

tasks = []

def add_task(task):
    """
    Add a task to the global task list.

    :param task: The task to add.
    :type task: str
    :raises ValueError: If the task is empty.
    :return: The updated list of tasks.
    :rtype: list

    Example:
        >>> add_task("Buy groceries")
        ['Buy groceries']
    """
    if not task:
        raise ValueError("Task cannot be empty.")
    tasks.append(task)
    return tasks

def list_tasks():
    """
    List all tasks.

    :return: The current list of tasks.
    :rtype: list
    """
    return tasks

def clear_tasks():
    """
    Clear all tasks.

    :return: A confirmation message.
    :rtype: str
    """
    tasks.clear()
    return "Tasks cleared."
```

---

### **Step 3: Initialize Sphinx**

1. Navigate to the `docs/` directory:
   ```bash
   cd docs
   ```

2. Run the `sphinx-quickstart` command:
   ```bash
   sphinx-quickstart
   ```

   Follow the prompts. For example:
   - **Project name**: `Task Manager`
   - **Author name**: Your name
   - **Separate source and build directories**: `yes`
   - **Autodoc extension**: `yes` (important for generating docs from Python code)

   This will generate a basic structure like this:
   ```
   docs/
   ├── build/
   ├── source/
   │   ├── conf.py         # Sphinx configuration file
   │   ├── index.rst       # Main documentation file
   │   └── _static/
   │   └── _templates/
   └── make.bat            # Build script for Windows
   └── Makefile            # Build script for Linux/Mac
   ```

---

### **Step 4: Configure Sphinx**

1. Open `source/conf.py` and configure:
   - Add the `project/` directory to the `sys.path` so Sphinx can find your Python modules:
     ```python
     import os
     import sys
     sys.path.insert(0, os.path.abspath('..'))  # Adjust path as needed
     ```

2. Enable the `autodoc` extension (already enabled if selected during setup):
   ```python
   extensions = [
       'sphinx.ext.autodoc',
   ]
   ```

---

### **Step 5: Document Your Code**

1. Use the `sphinx-apidoc` tool to generate ReST files for your Python module:
   ```bash
   sphinx-apidoc -o source ../tasks.py
   ```

   This will create a file like `tasks.rst` in the `source/` directory with documentation extracted from your docstrings.

2. Include the generated file in `index.rst`:
   Open `source/index.rst` and modify it to look like this:
   ```rst
   Welcome to Task Manager's documentation!
   =========================================

   .. toctree::
      :maxdepth: 2
      :caption: Contents:

      tasks

   Indices and tables
   ==================

   * :ref:`genindex`
   * :ref:`modindex`
   * :ref:`search`
   ```

---

### **Step 6: Build the Documentation**

1. Navigate to the `docs/` directory.
2. Run the following command to build the HTML documentation:
   ```bash
   make html
   ```

3. The generated HTML files will be in the `build/html/` directory. Open `index.html` in a browser to view your documentation.

---

### **Generated Documentation**

The HTML documentation will include:
1. A module-level overview from `tasks.py`.
2. Function-level documentation extracted from your ReST-style docstrings, including:
   - Parameter descriptions (`:param`).
   - Return types (`:rtype`).
   - Examples.

---

### **Key ReST Features Demonstrated**

#### **Headings**
In `tasks.py`, the module-level docstring uses `=` to create a heading:
```python
"""
Task Manager Module
===================
```

#### **Parameters and Types**
Used `:param` and `:type` to document parameters:
```python
:param task: The task to add.
:type task: str
```

#### **Return Values**
Used `:return` and `:rtype` to describe return values:
```python
:return: The updated list of tasks.
:rtype: list
```

#### **Raises**
Documented exceptions with `:raises`:
```python
:raises ValueError: If the task is empty.
```

#### **Code Blocks**
Examples were included using the `Example` section:
```python
Example:
    >>> add_task("Buy groceries")
    ['Buy groceries']
```

---

### **Next Steps**
1. **Explore Sphinx Extensions**:
   - `sphinx.ext.napoleon`: For Google/NumPy-style docstrings.
   - `sphinx.ext.viewcode`: Adds links to source code in the documentation.
   - `sphinx.ext.todo`: Adds support for `.. todo::` directives.

2. **Generate PDFs**:
   - Install `sphinx-rtd-theme` for better HTML output:
     ```bash
     pip install sphinx-rtd-theme
     ```
   - Add the theme in `conf.py`:
     ```python
     html_theme = 'sphinx_rtd_theme'
     ```


