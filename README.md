# Latexdiff Tutorial

[Latexdiff](https://ctan.org/pkg/latexdiff?lang=en) shows the difference between two LaTeX documents. Follow these steps:  

1. In the project directory, flatten latex files into two copies: `pre.tex` and `post.tex`.
2. Run this in terminal: `latexdiff pre.tex post.tex > diff.tex`
    - Choose a different style with latexdiff -t [OPTION]
    A `diff.tex` file will be generated.
3. Open `diff.tex` in local LaTeX Editor (e.g., Texifier), make changes if needed.
    - You can override styles at the end of the preamble. For example, to remove curly underlines for added text in the default `UNDERLINE` style, You can do so by inserting the following lines at the end of the preamble: 
	```latex
	\renewcommand{\DIFadd}[1]{\textcolor{blue}{#1}}  
	\renewcommand{\DIFaddbegin}{}  
	\renewcommand{\DIFaddend}{} 
	```
4. Compile `diff.tex` to PDF.
LaTeXdiff will generate a PDF that looks something like this:
![image](resources/example.png)

## Overleaf
Steps 1-2 can be done in Overleaf, with one additional step: under the root directory, create a file called `latexmkrc` with the following content:  
```pearl
$pdflatex = "latexdiff pre.tex post.tex > diff.tex; pdflatex %O diff";
```
This will automatically generate `diff.tex` when you compile the project.

- To modify `diff.tex`, one can try downloading the `diff.tex` file from Overleaf and then uploading it back.
## Resources
- [Latexdiff Manual](resources/manual.pdf)
