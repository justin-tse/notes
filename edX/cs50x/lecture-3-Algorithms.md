Algorithms
==========
### ddb
### Arrays
### Searching
### Running Times
Big O notation(maximally)
Omega notation(lower bound)
### Linear Search
### Binary Search
### numbers
- int main(void) why int?
Because it alway return 0 or 1, 0 is true and 1 is false. 0 means all  is well.
```c
#include <cs50.h>
#include <stdio.h>

int main(void)
{
    int numbers[] = {4, 6, 8, 2, 7, 5, 0};

    for (int i = 0; i < 7; i++)
    {
        if (numbers[i] == 0)
        {
            printf("Found\n");
            return 0;
        }
    }
    printf("Not found\n");
    return 1;
}
```
return 0 is well, right is only one way, means success, but return 1 is not necessary because wrong have different ways.
### names
### strcmp
strcmp(str1, str2)
compare the string, checks every characters in string for ASCII order, or ASCIIbetical, precedes left to right
return less 0, 0, greater than 0 
- less 0 means str1 is before str2
- 0 means str1 == str2
- greater than 0 means str 1 is after str2
when to stop, hit the null means after 8 bits

In bool expreesion, 0 is the only false number, other are all true
### structs
The following code is right but design of this code not necessarily the best. Code smell is bad.
```c
#include <cs50.h>
#include <stdio.h>
#include <string.h>

int main(void)
{
    string names[] = {"Brian", "David"};
    string numbers[] = {"+1-617-495-1000", "+1-949-468-2750"};

    for (int i = 0; i < 2; i++)
    {
        if (strcmp(names[i], "David") == 0)
        {
            printf("Found %s\n", numbers[i]);
            return 0;
        }
    }
    printf("Not found\n");
    return 1;
}
```
The more you can write code that's self-defensive that protects you from yourself, the better off you're going to be, the more correct your code is going to be, and the more easily you're going to be able to collaborate successfully, if you so choose in the real world, on real-world programming projects, whether for a research project, a full-time job, a personal project or the like.
Generally speaking, you should not trust yourself or other people that with whom you're writing code, you should have as many defense mechanisms in place exactly along these lines.
So the following is the better design:
```c
#include <cs50.h>
#include <stdio.h>
#include <string.h>

typedef struct
{
    string name;
    string number;
}
person;

int main(void)
{
    person people[2];

    people[0].name = "Brian";
    people[0].number = "+1-617-495-1000";

    people[0].name = "David";
    people[1].number = "+1-949-468-2750";

    for (int i = 0; i < 2; i++)
    {
        if (strcmp(people[i].name, "David") == 0)
        {
            printf("Found %s\n", people[i].number);
            return 0;
        }
    }
    printf("Not found\n");
    return 1;
}
```
### phonebook
### Selection Sort
If I am writing the best designed algorithm I could to analyze the data as efficiently as possible.
The trade-off is going to be between human time, complexity, or the amount of space or memory that you're using. And part of the art of being a good computer scientist, and in turn programmer, is trying to decide where the line is.
### Bubble Sort
Omega O(n)
O(n^2)
### Recursion
iterative
```
Pseudocode
Pick up phone book
Open to middle of phone book
Look at page
If Smith is on page
    Call Mike
Else if Smith is earlier in book
    Search left half of book
Else if Smith is later in book
    Search right half of book
Else
    Quit
```
recursion
```
Pseudocode
Pick up phone book
Open to middle of phone book
Look at page
If Smith is on page
    Call Mike
Else if Smith is earlier in book
    Open to middle of left half of book
    Go back to line 3
Else if Smith is later in book
    Open to middle of right half of book
    Go back to line 3
Else
    Quit
```
### Merge Sort
```
If only one number
    Quit
Else
    Sort left half of numbers
    Sort right half of numbers
    Merge sorted halves
```
### Visualizations