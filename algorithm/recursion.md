# Recursion


## 1.What is recursion?
The process in which a function calls inself directly or indirectlty is called
recurion and corresponding function is called as recursive function.Using
recursive algorithm, certain problems can be solved quite easily. Ex: Towers of
Hanoi(TOH), Inorder/Preoder/Postorder Tree Traversals, DFS of Graph,...

There are serveral ways of doing that but the simplest aproach is simply add the
numbers starting from 1 to n. So the function simply looks like,

> approach(1) - Simply adding one by one 
> f(n) = 1 + 2 + 3 + ... + n

but there is another mathematical approach of representing this,

> approach(2) - Recursive adding
> f(n) = 1      n = 1
> f(n) = n + f(n-1) n>1

The **approach(2)** the function **f()** itself is being called inside the function


## 2.What is the base condition in recursion 

The solution to the base case is provided and the solution of the problem is expressed
in terms of smaller problems

```cpp
int fact (int n )
{
    if (n <=1 )
        return 1;
    else 
        return n*fact(n-1);
}
```

if **Stack Overflow** error occurs in recursion, it happens because **the base case** is 
not reached or not defined.

## 3.What is the difference between direct and indirect recursion? 

A function fun is called direct recursive if it calls the same fun fun. A function
fun is called indirect recursive if it calls another function say fun_new and fun_new 
calls fun directly or undirectly. 

```cpp
// An example of direct recursion
void directRecFun()
{
    // Some code...
    directRecFun();

    // Some code...
}

// An example of indirect recursion
void indirectRecFun()
{
    // Some code...
    indirectRecFun2();

    // Some code...
}

void indirectRecFun2()
{
    // Some code...
    indirectRecFun();

    // Some code...
}
```
## 4.What is difference between tailed and not-tailed recursion ? 

A recursive function is tail recursive when recursive call is the las thing executed 
by the function. 


## 5.What are the disadvantages of recursive programming over iterative programming

Note that both recursive and iterative programs have the same problem-solving
powers,.. every recursive program can be written iteratively and vice versa is 
also true. The recursive program has greate space requirements than iterative 
programs as all functions will remain in the stack until the case is reached.
It also has greater time requirements because of function calls and returns overhead.

## 6.What are the advantages of recursive programming over iterative programming

Recursion provides a clean and simple way to write code. Some problems are inherently
recursive like tree traversals, TOH, etc. We can write such codes also iteratively with the 
help of a stack data stucture. For example, Inorder Tree Traverals with out Recusion, 
TOH,..

