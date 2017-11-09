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
