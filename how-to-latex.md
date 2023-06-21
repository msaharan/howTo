# how-to: LaTeX

Include a wide figure on top, two narrow figures on bottom.

\begin{figure}[htbp]
		\centering
	\begin{tabularx}{\textwidth}{XX}
		\includegraphics[width=0.49\textwidth]{wide-figure}  \\
		\includegraphics[width=0.49\textwidth]{narrow-figure1} &
		\includegraphics[width=0.5\textwidth]{narrow-figure2}\\		
	\end{tabularx}
	\caption{}
	\label{}
\end{figure}
```
