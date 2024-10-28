# 1	Preface
- Since the publication of this book the language C and computers in general changed A LOT.
- ANSI aimed to produce "an unambiguous and machine independent definition of the language C". It is the ANSI standard for C.
	- Gave constructors and enumerations
	- Added function declarations with cross-checking
	- Specifices a standard library
		- IO
		- mem management
		- string manipulation

## 1.1	Preface to the first edition
- C is a general purpose programming language
	- features economy of expression
	- modern flow control and data structures
	- rich set of operators
	- small and low level
	- minimal restrictions
- Designed to be used on UNIX
- This book is a tutorial
- This book assumes basic programming knowledge, and itsnt intro to programming

# 2	Tutorial Introduction
- Brief example that include basic concepts for a program
	- variables
	- constants
	- arithmetic
	- control flow
	- functions
	- IO
## 2.1	Hello World
```c
#include <stdio.h>

main()
{
	printf("hello, world\n");
}
```
> [!tip]
> - runnning the programs differes between Operation Systems
> 	- for UNIX the suffix is : "`.c`", and the command is : "`cc`" such that `cc hello.c` print `hello, world`

- A C program consists of *functions* and *variables*
	- A *function* containts *statements* that specify the compution operations to be done
	- A *variable* store values used during computation
- A C program must start with a function `main`, it begins execution
- `#include <stdio.h>` tells the compiler to include information about the standad input/output library

- A *function* gets *arguemnts* written inside its `()` and has *statements* written inside its `{}`. It ends with `;` signifying end of *statement*
- `\n` is an escape sequence and a newline character
## 2.2	Variables and Arithmetic Expressions
```C
#include <stdio.h>
/* print Fahrenheit-Celsius table
	for fahr = 0, 20, ..., 300 */
main()
{
	int fahr, celsius;
	int lower, upper, step;
	
	lower = 0;
	upper = 300;
	step = 20;

	fahr = lower;
	while (fahr <= upper) {
		celsius = 5 * (fahr-32) / 9;
		printf("%d\t%d\n", fahr, clesius);
		fahr = fahr + step;
	}
}
```
- `/* */` is a *comment* clause and ignored by the compiler
- *variables* must be declared before used, usually at the start of a *function*
- *declaration* is a list of variables and thier names. e.g. `int fahr, celsius`
- `while` is a loop. It tests a condition and if `true` it executes the body of the loop. until the condition is `false`
- C doesnt care about indentation and looks, but it helps the coders understand the logic. 
- in `printf` the string `%d` is an `integer` placeholder and `\t` is for a tab. 
- `printf` and input/output functions are not a part of C but are defined the same in most libraries
- `integers` are floored when operated upon, so the results can be inaccurate, when needed, use float
```c
#include <stdio.h>
/* print Fahrenheit-Celsius table
	for fahr = 0, 20, ..., 300 */
main()
{
	float fahr, celsius;
	float lower, upper, step;
	
	lower = 0;
	upper = 300;
	step = 20;

	fahr = lower;
	while (fahr <= upper) {
		celsius = 5 * (fahr-32) / 9;
		printf("%3.0f\t%6.1f\n", fahr, clesius);
		fahr = fahr + step;
	}
}

```
- printing `float` requires changing `%d` accordanly to `%x.yf` where x is minimiun characters to print and y is how many digit after the decimal point, for 3.0 and 6.1 its like so:
```md
  0	 -17.8
 20	  -6.7
 40	   4.4
 60	  15.6
 80	  26.7
100	  37.8
120	  48.9
140	  60.0
160	  71.1
180	  82.2
200	  93.3
220	 104.4
240	 115.6
260	 126.7
280	 137.8
300	 148.9

Process finished with exit code 0
```

| placeholder | explanation                                                                              |
| -------------- | ----------------------------------------------------------------------------- |
| %d             | print as deciaml integer                                                      |
| %6d            | print as decimal integer, at least 6 characters wide                          |
| %f             | print as floating point                                                       |
| %6f            | print as floating point, at least 6 characters wide                           |
| %.2f           | print as floating point, 2 characters after decimal point                     |
| %6.2f          | print as floating point, at least 6 characters wide and 2 after decimal point |
## 2.3	The For Statement
```c
#include <stdio.h>

/* Farenheit-Celsius table */
main ()
{
	for (int fahr = 0; fahr <= 300; fahr = fahr + 20)
		printf("%3d %6.1f\n", fahr, (5.0/9.0)*(fahr-32));
}
```
- `for (` start; limit; increments (or decrements); `)`
## 2.4	Symbolic Constants
- dont use 'magic numbers', give everything a name, use a constant if possible.
	- makes the code clean, clear and understanable
	- do it using `#define`
	- where a defined name is used a value is used instead
- The defined names `LOWER, UPPER, STEP` are called *Symbolic Constants*
	- written in ALL CAPS
	- no semicolon
```c
#include <stdio.h>

#define LOWER 0
#define UPPER 300
#define STEP 20

/* print Fahrenheit-Celsius table */
main()
{
	int fahr;

	for (fahr = LOWER; fahr <= UPPER; fahr + STEP)
		printf("%3d %6.1f\n", fahr, (5.0/9.0)*(fahr-32));
}
```
## 2.5	Character I/O
- input and output text is dealt as `text stream`
	- a sequence of characters followerd by a newline character
	- proccesed by a library
	- `c = getchar()`; gets the next character each time
### 2.5.1	File Copying
```c
#include <stdio.h>

/* copy input to output; 1st version */
main ()
{
	int c;

	while ((c = getchar()) != EOF) {
		putchar(c);
	}
}
```
- `EOF` is an *integer* defined in `stdio.h` that is different from any *char* value and is defined by [[The ANSI C Programming Language#2.4 Symbolic Constants]]
### 2.5.2	Character Counting
```c
#include <stdio.h>

/* count character in input */
main()
{
	long nc;

	nc = 0;
	while (getchar() != EOF)
		++nc;
	printf("%ld\n", nc);
}
```
- `++nc`: increment by one. `++nc` $\neq$ `nc++`
- `long` is 32 bits, less likely to overflow than 16 bits which hold $\frac{2^{16}}{2}-1=32767$ positive integers. 1 position for `0`, half for negative integers and half for positive integers.
- `ld` tells `printf` to print a *long* integer
### 2.5.3	Line Counting
```c
#include <stdio.h>

/* count lines in input */
main()
{
	int c, nl;

	nl = 0;
	while ((c = getchar()) != EOF)
		if (c == '\n')
			++nl;
	printf("%d\n",nl);
}
```
- $==$ checks equality
- `''` integers value equal to the numerical value of the character in the machines character set (ASCII)
### 2.5.4	Word Counting
```c
#include <stdio.h>

#define IN 1
#define OUT 0

main()
{
	int c, nl, nw, nc, state;

	state = OUT;
	nl = nw = nc = 0;
	while ((c = getchar()) != EOF) {
		++nc;
		if (c == '\n')
			++nl;
		if (c == ' ' || c == '\n' || c = '\t')
			state = OUT;
		else if (state == OUT) {
			state = IN;
			++nw;
		}
	}
	printf("%d %d %d\n", nl, nw, nc);
}
```
- expressions containing `||`, '&&' are read left to right
## 2.6	Arrays
```c
#include <stdio.h>

main()
{
	int c, i, white, nother;
	int ndigit[10];

	nwhite = nother = 0;
	for (i = 0; i < 10; ++i)
		ndigit[i] = 0;

	while ((c = getchar(c)) != EOF)
		if (c >= '0' && c <= '9')
			++ndigits[c-'0'];
		else if (c == ' ' || c == '\n' || c == '\t')
			++nwhite
		else
			++nother

	printf("digits =");
	for (i = 0; i < 10; ++i)
		printf(" %d", ndigit[i]);
	printf(", white space = %d, other = %d\n", nwhite, nother);
}
```