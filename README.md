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



