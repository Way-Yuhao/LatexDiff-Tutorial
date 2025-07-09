# Latexdiff Tutorial

LaTeXdiff shows the highlights of the difference between two LaTeX documents. Follow these steps:  

1. In the project directory, flatten latex files into two copies: `pre.tex` and `post.tex`.
2.  Run this in terminal: `latexdiff pre.tex post.tex > diff.tex`
	- Choose a different style with latexdiff -t [OPTION]
	A `diff.tex` file will be generated.
3. Open `diff.tex` in local LaTeX Editor (e.g., Texifier), make changes if needed.
	- You can override styles at the end of the preamble. For example, to remove curly underlines for added text in the default `UNDERLINE` style, you can do so by inserting the following lines at the end of the preamble: 
	```latex
	\renewcommand{\DIFadd}[1]{\textcolor{blue}{#1}}  
	\renewcommand{\DIFaddbegin}{}  
	\renewcommand{\DIFaddend}{} 
	```


