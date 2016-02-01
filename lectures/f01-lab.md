---
title: Introduction to C Lab
layout: lecture
mathjax: true
---


## Q1: What to do while the data is away?
![difficulty:easy]({{site.baseurl}}/assets/difficulty-easy-green.svg)

The Chrome web browser has a diagnostic tool which records the network loading times for any page you visit.
Below is a sample timeline for loading the CS207 homepage.

![Timeline]({{site.baseurl}}/lectures/f01/timeline.png)

It takes 108ms to retrieve all the page's data from the internet.

That's a *long* time for a computer to be waiting.
Let's figure out exactly how long by estimating what we could do with that time.

[AES](https://en.wikipedia.org/wiki/Advanced_Encryption_Standard), the Advanced Encryption Standard, is a common cryptographic algorithm for securing data.
Let's say you've "acquired" a list of AES-encrypted passwords from a nefarious, trench-coat-wearing "friend".
While we're waiting for our page to load, let's set to work breaking these passwords.

The most common methods for password cracking involve guessing random combinations, encrypting them, and checking against the encrypted list.
To simplify things, let's assume that everything except the encryption is free.
So we need to know how many passwords we can encrypt in 108ms.

Since [2010](https://software.intel.com/en-us/articles/intel-advanced-encryption-standard-aes-instructions-set), Intel CPUs have had special hardware built in which can compute AES in just a couple of instructions.
Specifically, recent Haswell chips have an average decryption rate of [0.89 cycles per byte](http://www.intel.com/content/dam/www/public/us/en/documents/white-papers/haswell-cryptographic-performance-paper.pdf) for 256-bit keys.
If we assume that all your passwords are less than 11 bytes long, and that our processor runs at 2GHz, how many passwords can we try in the time it takes the CS207 webpage to load?

## Q2: Fibonacci... again.
![difficulty:easy]({{site.baseurl}}/assets/difficulty-easy-green.svg)

#### Part 1: Do it.

Here is the recursive implementation of fibonacci from the previous lab:

```python
def fib(n):
    if n == 1:
        return 0
    if n == 2:
        return 1
    return fib(n-1) + fib(n-2)
```

Write it in C.

#### Part 2: Inspecting the stack

Compile your program with debugging symbols and load it into a debugger.

In most debuggers, breakpoints can be set not only on specific line numbers, but also on functions.
This creates a breakpoint on the first non-declaration statement in the function.
Set a breakpoint on your fibonacci function.

Run your program.
It should freeze inside the fibonacci function.
Now continue the program 10 times.
In `gdb`, if you press "enter" at the gdb prompt, it will repeat the last command you ran.
So here, to repeat 10 times, type `continue` and hit enter once, and then hit enter nine more times.

Print the call stack.
How many stack frames are currently on the call stack?
What is the current value of `n`?
(hint: you can either do this with `print` or you can inspect the output of `backtrace`)

## Q3: Crafting a buffer overflow attack
![difficulty:tricky]({{site.baseurl}}/assets/difficulty-tricky-red.svg)

You are now the nefarious, trench-coat-wearing "friend" from question 1.

#### Part 1: Get familiar

You're given the code below.
For all parts of this question, you aren't allowed to modify the source code at all.

```c
// overflow.c
#include <stdlib.h>
#include <stdio.h>

void win()
{
  printf("Success!\n");
  exit(0);
}

int victim_function(int index)
{
  int64_t a[5] = {1,2,3,4,5};
  a[index] = (int64_t)(&win);
  return 0;
}

int main(int argc, char **argv)
{
  int magic_number = 0;

  if( argc>1 ) {
    magic_number = atoi(argv[1]);
  } else {
    printf("Please enter a magic number.\n");
    return -1;
  }

  victim_function( magic_number );

  return 0;
}
```

Copy the code into a file and compile it.
The variables `argc` and `argv` are Unix's way of allowing C programs to interpret command-line arguments.
`argc` is an integer containing the 1 + number of arguments given.
`argv` is an array of strings.
The first element of `argv` is the name of the program you compiled, and the rest of the arguments are strings corresponding to command-line arguments.

When you run your program like this:

```
$ ./overflow 0
```

`argc` is automatically set to 2, `argv[0]` is set to `"/your/path/to/overflow"`, and `argv[1]` is set to `"0"`.
Additionally, the function `atoi` takes a string and converts it to an integer.
It's a stupid function, so if you pass it a string that isn't an integer, like `"hello"`, it will just return 0.
If you want, you can prove this to yourself by setting a breakpoint in gdb at the line with `atoi` and running `./overflow hello`.
You can print the value of magic_number.

#### Part 2: Staking out the target
TODO

(general idea behind buffer overflows)
(introduce `print/x` syntax)
(show that `./overflow 0` replaces `a[0]` with `&win`)
(backtrace to identify the program locations for each function)

#### Part 3: Springing the trap
TODO

(show you can use `p/x` to look at values beyond the array bounds)
(figure out which value is the return address)
(re-run the program with that offset)

(set a breakpoint on the function `win`)
(what does the call stack look like? why do you think this is?)
