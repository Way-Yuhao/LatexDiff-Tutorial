# Latexdiff Tutorial

Latexdiff shows highlights the difference betweent two latex documents. Follow these steps:  

1. In the project directory, flatten latex files into two copies: `pre.tex` and `post.tex`.
2.  Run this in terminal: `latexdiff pre.tex post.tex > diff.tex`
	- Choose a different style with latexdiff -t [OPTION]
	A `diff.tex` file will be generated.
3. Open `diff.tex` in local Latex Editor (e.g. Texifier), make changes if needed.
	- You can override sytles at the end of the preamble. For example, to remove curly underlines for added text in the defualt `UNDERLINE` style, You can do so by inserting the following lines at the end of the preamble: 
	```latex
	\renewcommand{\DIFadd}[1]{\textcolor{blue}{#1}}  
	\renewcommand{\DIFaddbegin}{}  
	\renewcommand{\DIFaddend}{} 
	```


