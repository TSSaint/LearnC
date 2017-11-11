# LearnC

## The Structure of a C Program
First things first is the need for something called a compiler, which converts your C Program into a binary form, which is directly understood by the machine. A compiler is just another program, but it requires precise input to work correctly!
<br>
C Programs require the adherance to a standard format and structure. The compiler program expects well-defined information, always.
<br>
All C code have an extension with ".c" that tells the compiler where the program lives. The first thing to do is to write the following:
```c
#include <stdio.h>
int main()
{
  /* some program */
  int a;
  scanf("%d", &a);
  printf("You entered &d\n", a);

  return 0;
}
```

## #include <stdio.h> and Directives
This is called a "pre-processor directive". These are instructions to the compiler that converts your C program into machine-understandable form. It tells the compiler that it needs to do certain things, in this case access the "stdio library", which contains various useful functions to be utilized in a C program. This is the most common directive used in C.
<br>
Typically in the beginning of C programs, any kinds of libraries are specified that tells the program what to include!

## int main()
This is a function!<br>
Functions are the building blocks of programs.<br>
int main() is a required, or main entry point, of any C program. The C runtime brings control to the very first line of the main function. It is mandatory. It basically returns and integer and takes no arguments.

## { curly brace }
The body of the main function exists between curlies. The body of some function always contains statements and comments or such. The body is where you specify some series of commands, or even functions, inside the program. This is where and what gets done.<br>
Comments, which can help others and take notes of what functions do, are laid out like:
```c
/* SOME COMMENT */
```

## int a;
This is the declaration of a variable "a", and that it is an integer.<br>
Variables are containers that hold different data! There are many kinds of types of data that the C compiler understands.

## scanf... printf
This piece of the program are just function calls which read input from users and output messages to the screen. stdio.h stands for standard input and output, which describes the kinds of functions exist in that library.

----

# C Data Types
## Integers
Integers can be stored as follows (most ints are 4 bytes in the modern day). These are important when considering dynamic memory allocation:
- Short: 2 bytes, 16 bits
- Int: 2 bytes, 16 bits
- Long: 4 bytes, 32 bits
<br>
If datatype has 16 bits, it can be represented with a unique combination of 2^16 capacity of these types. Since one of the bits are used to store the sign of the integer, their ranges will actually be about -2^15 to +2^15 (-32,768 to 32,767).
<br>
Comparatively, long ints will have about -2^31 to +2^31 or about -2.147 million to 2.147 million in length.
<br>
#### What Happens if A Variable Exceeds it's Range?
Let's say we add a '1' to the maximum of a short datatype (2 bytes).<br>
We must do binary arithmetic and add/pushes digits to the left up by one.
<br>Ex.
<br>32767 = 0111 1111 (+ 1)
<br>result
<br>-32768(!!) = 1000 0000
Generally, it is dangerous to carry out operations that use datatypes near the limits of their capacity. This can result in an "overflow", where a relatively simple numerical operation results in a very incorrect output.

## C Syntax with Data Types

#### Short & Long
When using short and long, we can do as follows:
```c
/* we can omit the "int" as the compiler will know */
long int i;
long i; 
short int i;
short i;
```
<br>

#### Signed/Unsigned
These can be used to store positive and negative integers.<br>
If we can declare a variable to be unsigned (if we are already aware of the number's sign), then we can consider the limit of the variables to be 0 to 2^16 or 65536. Likewise, a long unsigned int can store 2^16 or up to 4294967295!<br>
Ex.
```c
/* unsigned variable */
unsigned int students;

/* long/short unsigned ints */
long usigned int;
short usigned int;

```


## Floating Point/Decimal
For Int Long/Short types, numbers that do not have numbers after their decimal points. C supports floating points or decimal data types. Consider that datatypes for decimals are well understood by the C compiler and are the following.<br>
Floating point data type bit limits consist of m times E raised to the power of n, where exponent n is an integer, and the coefficient m is any real number.
<br>m * x E^n, where E = 2.718
<br>
These numbers are incredibly large, but do well for their relatively small size.<br>
- Float 4 bytes, -3.4 E 38 to +3.4 E 38
- Double 8 bytes, -1.7 E 308 to +1.7 E 308
- Long Double 10 bytes, -1.7e4932 to +1.7e4932
Ex.
```c
/* floating point */

```

## Text
The string datatype is denoted with 'char'. Char is a basic datatype in C and is used to hold a single character.
- Char 1 byte, 256<br>
We can store the value of a single character by enclosing it in single quotes.<br>Ex.
```c
char a, b, c;
  a = 'Art';
  b = 'Bot';
  c = 'Cot';
```
<br>

NOTE:
We know that computers can only understand strings, right?<br>
So how does a computer/compiler know to understand keystrokes?<br>

## How Do Computers Recognize Characters?
This is an important concept that explains how programming languages can understand languages, like C, get around the limitation of computers only understanding bits. 
#### ASCII/UTF-8
The American Standard Code for Information Interchange enforces a standard that literally describe the required numerical representations of characters, like 'a - z' and '! - +
', or some action.<br>
All the keys on a keyboard have an ASCII code - it's basically a mapping between characters to fingers. 
<br>Ex.<br>
| a | ASCII CODE 097 | Binary 01100001 |<br>
| b | ASCII CODE 098 | Binary 01100010 |<br>
| c | ASCII CODE 099 | Binary 01100011 |<br>
...<br>
| r | ASCII CODE 114 | Binary 01110010 |<br>

The resulting impact of this standardization is a uniform way for users to talk to computers!
<br>
The C language is basically "faking" the contents of a variable by putting in a number.
<br>Ex.
```c
/* the ASCII character of letter */
a = 'F';
b = 'G';
/* is the same as */
a = 70;
b = 71;
```
Characters are more or less represented by numeric values. Basically, the char datatype can be treated as an even smaller version of the short type.<br>
#### The implication of this is that arithmetic operations can be performed on int, float, and chars datatypes!
Integers and characters can somewhat be used interchangeably when executing operations.<br>
Be careful to carefully write these operations, or you may experience the problem of truncation.
<br>Ex.
```c
/* z will be 195, as ASCII values of 'a' and 'b' are 97 and 98 respectively*/
char x, y;
   int z;
 x = 'a';
  y = 'b';
 z = x + y;
 /*z = 97 + 98*/
```

----

# If/Else: The Concept
In computer science and in life, we always have to make decisions!<br>
As we make decisions in the tangible world, we need a way to make computers simulate the ability to make decisions. It turns out that both worlds aren't very different - apparently, even the simplest computer science problems are modeling the "real" world. In C we use if/else statements Wto execute singular or multiple instructions in the if/else statement.<br>

## If then Else
We make decisions in every step of our lives.<br> 
For example, let's take apart a day - each decision we make builds upon the next, and culminates in the resulting outcomes of our lives.<br>Ex.
```c
/* rainy day */
if 'raining outside'
  'carry an umbrella'

/* work schedule */
if 'tomorrow is a work day'
  'set an alarm the night before'
 else
  'plan dinner with friends'
 
/* specific scheduling */
if 'tomorrow is a work day'
  'set an alarm the night before'
 else
  if 'start of a 3-day weekend'
   'set an alarm - go on a road trip'
  else
   'plan dinner with friends'
```
Making decisions is a core concept in computer programming - all programming languages support this ability to execute "IF/ELSE" statements.
<br> 

## Decision Control Structures
Take the example:<br>
Ex.
```c
/* the umbrella examble */
/* not raining by default */
int bIsRaining = 0;
printf("Is it raining? Enter 1 if yes.");
scanf("%d", &bIsRaining);
/* if statement, single-statement execution */
if (bIsRaining == 1)
 printf("It's raining - bring an umbrella!");
```
There are typically 3 parts of an if statement.<br>
1. Condition<br>
This is something that is checked, usually to see if something is true or not.
<br>
A logical test that evaluates to True or False.<br>
note: In C, any Non-zero value is "true", whereas a Zero value is "false". This very important detail to consider. Positive OR negative values are treated as true.

2. Scope<br>
This is typically executed if the checked condition matches the scope.
<br>
If the condition we're testing are true, some commands are executed.<br>
note: No curly braces are required if the scope of the if statement consists of a single command
<br>otherwise,
The scope must be enclosed in curly braces. This is mandatory - otherwise called a compound statement. If this is not included, the C compiler will not know what do do with the multiple lines. It does not hurt to always use curly braces. Remember, the if-scope can contain anything, including more if-else statements or NESTED if statements!
Ex.
```c
/* multi-statement execution */
int bIsRaining = 0;
 printf("Is it raining? Enter 1 if yes.");
 scanf("%d", &bIsRaining);
 { if (bIsRaining == 1)
  printf("It's raining - bring an umbrella!");
  printf("Do not wear anything else but boots!");
  printf("Don't lose the umbrella!");
 }
```

3. Statement(s)<br>
There can be multiple statements in scope, or in the If block. All commands are executed in this block/if the scope is passed.

# Evaluation
How do we evaluate the condition of an if/else statement?



