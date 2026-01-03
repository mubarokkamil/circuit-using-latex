# Lesson-4: Series-Parallel Connection

## Two Resistors in Series
```latex
\begin{circuitikz}
    % First resistor R1 from (0,0) to (3,0)
    \draw (0,0) to[R, l=$R_1$] (3,0);

    % Second resistor R2 from (3,0) to (6,0)
    \draw (3,0) to[R, l=$R_2$] (6,0);
\end{circuitikz}
```

Output:  

<p align="center">
  <img src="images/l1-4.png" alt="Single Resistor Circuit">
</p>


If you want the labels under the resistors:
```latex
\begin{circuitikz}
    \draw (0,0) to[R, l_=$R_1$] (3,0);
    \draw (3,0) to[R, l_=$R_2$] (6,0);
\end{circuitikz}
```

Output:  

<p align="center">
  <img src="images/l1-5.png" alt="Single Resistor Circuit">
</p>

Explanation:  
- `l_` = places the label below the resistor
- Useful if top space is crowded in your diagram

