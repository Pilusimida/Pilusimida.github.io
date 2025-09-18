---
layout: post
title: Introduction to Symbolic Computation Package(Sympy)
date: 2026-09-15
categories: [DML]
---
# SymPy: Symbolic Computing in Python

## Overview

SymPy is a pure Python library for symbolic mathematics. It provides computer algebra capabilities without requiring any external libraries.

## Key Features

### 1. Symbolic Variables
```python
from sympy import symbols, Eq

x, y, z = symbols('x y z')
expr = x**2 + 2*x*y + y**2
```

## 2. Algebraic Manipulation
```python
from sympy import expand, factor, simplify

expr = (x + y)**3
expanded = expand(expr)      # x³ + 3x²y + 3xy² + y³
factored = factor(expanded)  # (x + y)³
```

## 3. Calculus Operations
```python
from sympy import diff, integrate, limit

# Differentiation
derivative = diff(x**3, x)   # 3x²

# Integration
integral = integrate(x**2, x)  # x³/3

# Limits
lim = limit(sin(x)/x, x, 0)   # 1
```

## 4. Equation Solving
```python
from sympy import solve

# Algebraic equations
solutions = solve(x**2 - 4, x)  # [-2, 2]

# Systems of equations
solutions = solve([x + y - 3, x - y - 1], (x, y))  # {x: 2, y: 1}
```

## 5. Linear Algebra
```python
from sympy import solve

# Algebraic equations
solutions = solve(x**2 - 4, x)  # [-2, 2]

# Systems of equations
solutions = solve([x + y - 3, x - y - 1], (x, y))  # {x: 2, y: 1}
```

# 6. Printing and Visualization
```python
from sympy import series, fourier_transform

# Taylor series expansion
taylor_series = series(sin(x), x, 0, 5)  # x - x³/6 + O(x⁵)

# Fourier transform
ft = fourier_transform(exp(-x**2), x, k)
```

# 7, Physics and Advanced Mathematics
```python
from sympy import series, fourier_transform

# Taylor series expansion
taylor_series = series(sin(x), x, 0, 5)  # x - x³/6 + O(x⁵)

# Fourier transform
ft = fourier_transform(exp(-x**2), x, k)
```
# Installation
```bash
pip install sympy
```
# Basic Usage Example
```python
from sympy import *

# Define symbols
x, y = symbols('x y')

# Create and manipulate expressions
expr = (x + y)**2
expanded_expr = expand(expr)  # x² + 2xy + y²

# Solve equations
solution = solve(x**2 - 4, x)  # [-2, 2]

# Calculus
derivative = diff(sin(x), x)   # cos(x)
integral = integrate(x**2, x)  # x³/3
```