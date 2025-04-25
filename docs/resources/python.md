---
layout: page
title: Python FAQs
permalink: /resources/python/
nav_order: 2
parent: Resources
---

# Python FAQs
## Anaconda

## Jupyter Notebook
### How do I choose a kernel in Jupyter Notebook?
To choose a kernel in Jupyter Notebook, you can do the following:
1. Open the Jupyter Notebook.
2. Click on the "Kernel" menu at the top of the notebook.
3. Select "Change kernel" from the dropdown menu.
4. A list of available kernels will appear. Select the kernel you want to use.
5. The kernel will be changed, and you can start using it in your notebook.

### How do I export a Jupyter Notebook to PDF?
To export a Jupyter Notebook to PDF, you can do the following:
1. Open the Jupyter Notebook you want to export.
2. Click on the "File" menu at the top of the notebook.
3. Select "Download as" from the dropdown menu.
4. Choose "PDF via LaTeX" from the list of options.
5. The notebook will be converted to PDF and downloaded to your computer.
   
If your machine does not have LaTeX installed, you can simply export the notebook to HTML and then print it to PDF:
1. Open the Jupyter Notebook you want to export.
2. Click on the "File" menu at the top of the notebook.
3. Select "Download as" from the dropdown menu.
4. Choose "HTML" from the list of options.
5. Open the downloaded HTML file in a web browser.
6. Print the HTML file to PDF using the print dialog in your web browser.

## NumPy
### How do I scale a function operating over a vector to a matrix?
You can use double-loops to apply a function to each element of a matrix. For example, if you have a function `f` and a matrix `A`, you can do the following:
```python
import numpy as np

A = np.array([[1, 2], [3, 4]])
def f(x):
    return x**2
A_scaled = np.zeros(A.shape)
for i in range(A.shape[0]):
    for j in range(A.shape[1]):
        A_scaled[i, j] = f(A[i, j])
```

However, this is not the most efficient way to do it. Instead, you can use NumPy's vectorized operations to apply the function to the entire matrix at once:
```python
import numpy as np
A = np.array([[1, 2], [3, 4]])
def f(x):
    return x**2
A_scaled = f(A)
```

## SymPy
### How do I install SymPy?
If you use Anaconda, you can install SymPy using the following command:
```bash
conda install sympy
```
If you use pip, you can install SymPy using the following command:
```bash
pip install sympy
```
### Should the order of the variables in the `symbols` function matter?
No, the order of the variables in the `symbols` function does not matter. For example, the following two lines of code are equivalent:
```python
from sympy import symbols
x, y = symbols('x y')
```
```python
from sympy import symbols
x, y = symbols('y x')
```