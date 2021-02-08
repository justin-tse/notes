
```c
#include <stdio.h>

int main(void)
{
  int n = 50;
  printf("%i\n", n);
}
```
- &
ampersand
&n what is the address of n
```c
printf("%p\n", &n);
```
- '*'
*n  go to that adress 
so is undo the &n means n
```c
printf("%i\n", *&n);
```
- pointer
- pointer 8 bytes

- string
String s = "HI!" 

H | I | ! | \0
--- | :---: | --- | ---
0x123 | 0x124| 0x125 | 0x126

every char use 1 byte but the adreess is continuous.
