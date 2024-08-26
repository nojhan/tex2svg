# tex2svg

Convert LaTeX to SVG. A typical use would be to turn formulas into images, in order to be used in presentations or other integrated visualizations.

## Usage

Call the program as ``tex2svg [--preamble <LATEX_CODE>] [LATEX_CODE] [TARGET_FILE]``.

## Examples

Minimal example:
```sh
tex2svg '$$\exp(i\cdot\pi) + 1 = 0$$' > formula.svg
```

Specify a LaTeX preamble command:
```sh
tex2svg --preamble '\DeclareMathOperator*{\argmin}{arg\,min}' '$\argmin_{x\in X} f(x)$' formula.svg
```

Pipe in a multi-line LaTeX file as input:
```sh
cat file.tex | tex2svg > fig.svg
```
Or (alternatively);
```sh
tex2svg < file.tex > fig.svg
```

Indicate the output file as an argument:
```sh
tex2svg '$$\exp(i\cdot\pi) + 1 = 0$$' formula.svg
```


## Requirements

The tool requires ``pdflatex``, ``pdf2svg`` to be available. These can easily be installed (under a Debian-like Linux distribution) via:

 ```sh
 sudo apt install pdflatex pdf2svg
 ```

## Installation

Currently, there is no automated installation.

To install manually, type (as root):

```sh
git clone https://github.com/yannikschaelte/tex2svg
mkdir /opt/tex2svg/
cp tex2svg/tex2svg /opt/tex2svg/
cp tex2svg/latex_template.tex /opt/tex2svg
echo 'export PATH="$PATH:/opt/tex2svg/"' >> ~/.bashrc
```

