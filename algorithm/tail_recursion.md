# Tail Recursion

## What is tail recursion ?

**A recursive function** is tail recursive when recursive call is the las thing 
executed by the function. 

```c
void print(int n)
{
    if (n < 0 ) return;
    cout << " " << n;

    // The last executed statement is recursive call
    print(n-1);
}

```

The function **print()** is tail recursive.


## Why do we care ?

**The tail recursive** functions condidered **better** than **non-tail recursive** functions 
as tail-recursion can be optimized by compiler. The idea used by compilers to 
optimized tail-recursive functions os simple, since the recursive call is the last
statement, there is nothing left to do in the current function, so saving the 
current functions's stack frame is of no use. 

## Can a non-tail recursive function be written as tail-recursive to optimize it?

Consider the following function to calculate factorial of n. It is a non-tail-recursive
function. Although it looks like a tail recursive at first look. If we take a closer look, 
we can see that the value returned by **fact(n-1)** is used in **fact(n)**, so the call to
**fact(n-1)** is not the last thing done by **fact(n)**

```cpp

#include<iostream>
using namespace std;

unsigned int fact (unsigned int n )
{
    if (n == 0) return 1;
    return n * fact(n-1);

}

int main()
{
    cout << fact(5);
    return 0;
}
```
Some laguages recognize this and implement `proper tail calls` or `tail call elimination`
if they see a recursice call in tail position, they actually compile it into a
jump that reuses the current stack frame instead of calling the function normally.
This improve the memory useage of the funcion *asymptotically* and prevents it 
from overflowing the stack. 


