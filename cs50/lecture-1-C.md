## Start 2021.01.11
## 2021- Lecture 1 - C
### C
- When writing code, we might consider the following qualities:
  - **Correctness**, or whether our code works correctly, as intended.
  - **Design**, or a subjective measure of how well-written our code is, based on how efficient it is and how elegant or logically readable it is, without unnecessary repetition.
  - **Style**, or how aesthetically formatted our code is, in terms of consistent indentation and other placement of symbols. Differences in style don’t affect the correctness or meaning of our code, but affect how readable it is visually.
### hello, world
### Compiling
souce code -> compiling -> machine code
make hello -> hello.c -> call hello
### Functions
- arguments -> fuctions -> 
- Functions can also have two kinds of outputs:
    - **side effects**, such as something printed to the screen,
    - and **return values**, a value that is passed back to our program that we can use or store for later.
        - The “ask” block in Scratch, for example, created an “answer” block.
- To get the same functionality as the “ask” block, we’ll use a library
### Return Values
### Variables
### Format Codes
### CS50 Library
### main
### Header Files
### help50
### Style
### style50
### check50
### CS50 IDE's File Browser
### CS50 IDE's Command-Line Interface
### Types
### Format Codes
### Operators
### addition
### Integer Overflow
### truncation
### Typecasting
### Syntactic Sugar
### Conditions
### agree
### Boolean Expressions
### Loops
### get_positive_int
### Scope
### Mario
### Floating-Point Imprecision
### Integer Overflow

## Data Type
int 32bits(8 bytes) -2^31 ~ 0 ~2^31-1
unsigned int 32bits(8 bytes)  0 ~ 2^32-1

## Conditional Statements
- if (and if-else, and if-else if-else-...-else, and if if if-...-else)
- switch()
```c
int x = GetInt();
switch(x)
{
  case 1:
     print("One!\n");
     break;
  case 2:
     print("Two!\n");
     break;
  case 3:
     print("Three!\n");
     break;
  default:
     printf("Sorry!\n");
}

```
- ?:
Use to replace a very simple if-else to make your code look fancy.
```c
int x
if (expr)
{
  x = 5;
}
else
{
  x = 6;
}

int x = (expr) ? 5 : 6
```
## Loops
- while
- do-while
Use when you want a loop to repeat an unknown number of times, but at least once.(Ask to input)
- for
## Command line 
- rm -r  r means recursive
- rm -r can remove the directory
- cp -r can copy the directory
The "-r" stands for recursive, and tells cp to dive down into the directory and copy everything inside of it(including any subdirectories it might contain).

- If you wish to explore other interesting ones before we see them in the class, read up on:
chmod
ln
touch
rmdir
man
diff
sudo
clear
telnet

