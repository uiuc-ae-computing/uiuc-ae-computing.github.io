---
layout: page
title: Latex FAQs
permalink: /resources/latex/
nav_order: 2
parent: Resources
---

# Latex FAQ
This page contains some frequently asked questions about using LaTeX. 
If you have any questions that are not answered here, please feel free to reach out to us.
If you have any suggestions for improving this page, please let us know.

## Math Mode
### How do I insert an equation?
To insert an equation, you can use the `equation` environment.
```latex
\begin{equation}
    E = mc^2
\end{equation}
```
This will create a numbered equation. If you don't want the equation to be numbered, you can use the `equation*` environment instead.
```latex
\begin{equation*}
    E = mc^2
\end{equation*}
```
You can also use the `align` environment to align multiple equations.
```latex
\begin{align}
    E &= mc^2 \\
    F &= ma
\end{align}
```
This will create a set of aligned equations, with the `&` symbol indicating where to align the equations.
You can also use the `align*` environment to create unnumbered aligned equations.
```latex
\begin{align*}
    E &= mc^2 \\
    F &= ma 
\end{align*}
```
### How do I insert a matrix?
To insert a matrix, you can use the `matrix` environment.
```latex
\begin{matrix}
    1 & 2 & 3 \\
    4 & 5 & 6 \\
    7 & 8 & 9
\end{matrix}
```
This will create a matrix with no brackets. If you want to add brackets, you can use the `pmatrix` environment for parentheses or the `bmatrix` environment for square brackets.
```latex
\begin{pmatrix}
    1 & 2 & 3 \\
    4 & 5 & 6 \\
    7 & 8 & 9
\end{pmatrix}
```
```latex
\begin{bmatrix}
    1 & 2 & 3 \\
    4 & 5 & 6 \\
    7 & 8 & 9
\end{bmatrix}
```
You can also use the `vmatrix` environment for vertical bars or the `Vmatrix` environment for double vertical bars.
```latex
\begin{vmatrix}
    1 & 2 & 3 \\
    4 & 5 & 6 \\
    7 & 8 & 9
\end{vmatrix}
```
```latex
\begin{Vmatrix}
    1 & 2 & 3 \\
    4 & 5 & 6 \\
    7 & 8 & 9
\end{Vmatrix}
```
### How do I reduce too much space between equations?
To reduce the space between equations, check if there are any `\\` commands that are not needed.
If you are using the `align` environment, you can also use the `\vspace` command to add or remove space between equations.
```latex
\begin{align}
    E &= mc^2 \\
    \vspace{-0.5cm} % reduce space
    F &= ma
\end{align}
```

