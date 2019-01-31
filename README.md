# texfuck ─ A small, dirty Brainfuck interpreter written in TeX

## Usage

To execute from the console, use:
```sh
tex bf
```
or some derivative (e.g. `pdftex`, `pdflatex` etc.)

Alternatively, it may be included in a LaTeX document using:
```LaTeX
\input{brainfuck}
```
then calling `\brainfuck [program]^`.

Example: `\brainfuck ++++++++[>++++++++<-]>+.^` evaluates to `A`

## Problems

This implementation is _very dirty._
TeX's `\count` variables are used to hold memory tape values, this leads to two problems:

 - There are only 256 possible memory positions :(
 - Some positions are used for other stuff, so you may **overwrite important TeX values! D:**

**_I take no responsibility for the consequences of the last point should it occur!_**
I have attempted to alleviate this by imposing bounds on accessible memory.

## Idiosyncratica:

 - Input is in numbers but output is in the default encoding
 - Programs must end with the `^` when called in a program