# Lesson 1: Introduction to LaTeX and Circuitikz in Overleaf

## 1. Introduction
**Circuitikz** is a powerful LaTeX package used by Electrical Engineers to create professional, publication-quality circuit diagrams. Unlike drag-and-drop tools, Circuitikz uses code to define components, ensuring perfect alignment and standard symbols.

## 2. Basic Structure
Every circuit drawing requires a specific setup in the LaTeX preamble.

### The Skeleton Code
```latex
\documentclass{article}
\usepackage{circuitikz} % Essential package for circuits

\begin{document}
    \begin{circuitikz}
        % Drawing commands go here
    \end{circuitikz}
\end{document}
```

## 3. The `\draw` Command
The fundamental command to place components is `\draw`. It works on a Cartesian coordinate system (x, y).

Syntax:  
```latex
\draw (starting_point) to[component_type, label] (ending_point);
```   
Example:  
```latex
\draw (0,0) to[R, l=$R_1$] (3,0);
```
Key Rules:  
- Coordinates: Defined as `(x,y)`. E.g., (0,0).
- The Connector: The keyword to connects two coordinates.
- The Component: Inside square brackets `[...]`. E.g., [R] for Resistor.
- The Semicolon: Every path must end with `;`. 

## 4. Labeling Components (MOST IMPORTANT)
Horizontal Label (Above the Component):  
```latex
\draw (0,0) to[R, l=$R_1$] (3,0);
```

- l= → label
- `$R_1$` → LaTeX math notation for subscript

Horizontal Label (Below the Component):  
```latex
\draw (0,0) to[R, l_=$R_1$] (3,0);
```
- `l_` →  Below the Component


## 5. Common Component Labels

| Component      | Syntax      |
| -------------- | ----------- |
| Resistor       | `to[R]`     |
| Capacitor      | `to[C]`     |
| Inductor       | `to[L]`     |
| Voltage source | `to[V]`     |
| Current source | `to[I]`     |
| Wire           | `to[short]` |


## 6. Drawing Multiple Components in Series (Two Methods)

When drawing components in series, there are two valid approaches in `circuitikz`.
Both work, but one is recommended.

🔹 Method 1:  
```latex
\begin{circuitikz}
    \draw (0,0) to[R, l=$R_1$] (3,0);
    \draw (3,0) to[R, l=$R_2$] (6,0);
\end{circuitikz}
```

🔹 Method 2- Chaining: (Recommended)  
```latex
\begin{circuitikz}
    \draw (0,0) to[R, l=$R_1$] (3,0)
              to[R, l=$R_2$] (6,0);
\end{circuitikz}
```

Example:  
Three Resistors in Series (Chaining Method)
```latex
\begin{circuitikz}
    \draw (0,0) to[R, l=$R_1$] (3,0)
              to[R, l=$R_2$] (6,0)
              to[R, l=$R_3$] (9,0);
\end{circuitikz}
```
- The semicolon `;` appears only once, at the end



