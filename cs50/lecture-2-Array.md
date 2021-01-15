## Arrays
### clang
Clang is the compiler, which is a program that converts source code to machine code.
clang hello.c
out*
clang -o hello hello.c (-o output, hello rename, hello.c the target, three command line arguments)
hello*

clang -o hello hello.c -lcs50(link in the CS50 library, means make sure to incorporate all of th machine code from CS50's library into your program as well)
```shell
~/ $ make hello 
clang -ggdb3 -O0 -std=c11 -Wall -Werror -Wextra -Wno-sign-compare -Wno-unused-parameter -Wno-unused-variable -Wshadow    hello.c  -lcrypt -lcs50 -lm -o hello
```
for example
-lm link a math library
-lcrypt link a cryptography or encryption library

### compiling
"Compiling" mean these 4 steps
- preprocessing

read your code # and search then change

For example …
```c
#include <cs50.h>
#include <stdio.h>

int main(void)
{
    string name = get_string("What's your name? ");
    printf("hello, %s\n", name);
}
```

… will be preprocessed into:
```c
...
string get_string(string prompt);
int printf(string format, ...);
...

int main(void)
{
    string name = get_string("Name: ");
    printf("hello, %s\n", name);
}
```
This includes the prototypes of all the functions from those libraries we included, so we can then use them in our code.
- compiling
Compiling takes our source code, in C, and converts it to another type of source code called assembly code, which looks like this:
```asm
...
main:                         # @main
    .cfi_startproc
# BB#0:
    pushq    %rbp
.Ltmp0:
    .cfi_def_cfa_offset 16
.Ltmp1:
    .cfi_offset %rbp, -16
    movq    %rsp, %rbp
.Ltmp2:
    .cfi_def_cfa_register %rbp
    subq    $16, %rsp
    xorl    %eax, %eax
    movl    %eax, %edi
    movabsq    $.L.str, %rsi
    movb    $0, %al
    callq    get_string
    movabsq    $.L.str.1, %rdi
    movq    %rax, -8(%rbp)
    movq    -8(%rbp), %rsi
    movb    $0, %al
    callq    printf
    ...
```
- assembling
convert this assembly code into machine code
- linking
hello.c and cs50.c and stdio.c
- When we install a IDE and language, we have preprocessed the libray in our computer to make it more efficent, so most of the time, we only need to compilie the code and linking. 

## debug
- style50
- help50
- check50
- printf
## printf
Instincts to debug
## debug50
First time you will feel use debug tool slower than use printf because it has a bit of a learning curve.
After you master it, you will save many time return.
### Duck Debugging
A wonderful proxy for that conversant partner -> Duck
Talk a duck or other animal. Talk even aloud or think aloud.
It's just a wonderful compelling habit to get into because just in hearing yourself vocalize what you think is logical will the illogical very often jump out at you instead.
### Memory
1 byte = 8 bits
bool 1 byte
char 1 byte (ASCII 8 bits 256)
int 4 bytes
long 8 bytes
float 4 bytes
double 8 bytes
string ? bytes
When power off the files will not be saved because RAM, memory, is volatile. It requires electricity to continue powering it.
When we runing a program in C it is indeed, by definition, running in your computer's memory. Variable will store in memory. Bytes in your chip in memory.
### Scores
truncation
In mathematics and computer science, truncation is limiting the number of digits right of the decimal point.
### Array
### ASCII
placeholder
%c 
%d
%ld
%f
%lf
%i
printf("%i", "#") => 35 
### Strings
\0(ASCII is 0, eight 0 bits) as the null character, represents the end of a string.
string str = "H!!"
need 4 bytes to store "HI!"
### Strlen
<string.h>

### Arrays of strings
### to upper
ASCII "a" - "A == 32
<ctype.h>
islower(s[i])
isupper(s[i])
toupper(s[i])

### Command-line arguments
argc: argument count
arrv: arrays of vector
int main()
why int, because function always end in 0. And as notes, they use 0 to connote that nothing has gone wrong, that all as well.
> int main – 'int main' means that our function needs to return some integer at the end of the execution and we do so by returning 0 at the end of the program. 0 is the standard for the “successful execution of the program”. main – In C89, the unspecified return type defaults to int.

### exit status
return 1, means something wrong
return 0, means nothing wrong
```bash
echo $?
```
can see what was my exit status.
### readability
### cryptography
plaintext -> cipher -> ciphertext
need the key to decode