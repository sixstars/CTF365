# Day 3
## Pre knowledge
To solve this challange, you need to know the structure of stack.
If you don't know what is stack, just google it.

All most parameters of function call and local variables in functions are saved in the stack.
The order of parameters in stack is decided by the order you write it and the rules of calling functions.
The order of local variables is decided by the order you define it and the compiling parameters.

As we compile the program with certain parameters, the variable `val` is located immediately after the array variable `buf`. While the `c/c++` would not check the legitimacy of index when access a element of array, you can access `val` by `buf[20]` in these two programs.
## Solution - `simplified`
As you can see, the length of array `buf` is 20, while `scanf()` accept a input string with length 21. So you can directly do the overflow with input `AAAAAAAAAAAAAAAAAAAAW`.
## Solution - `narnia0`
It's nearly same as `simplified`. However, you should input some special characters, which situation you will always meet in exploition.

The usual way is using Python to output it. Don't forget the endian issue. So you can get the input string with Python script `print 'A'*20+'\xef\xbe\xad\xde'`

But you will find that you don't get a shell from the program. Why? Because the bash add an `EOF` at the end of the string which python output. Although the program executes the `/bin/sh`, getting an `EOF` will end the shell. So, if you want to send a command to the program to execute in `/bin/sh`, you can run `(python -c 'print "A"*20 + "\xef\xbe\xad\xde"'; echo "id") | /narnia/narnia0`. Don't use `(python -c 'print "A"*20 + "\xef\xbe\xad\xdeid"')` because the `scanf()` just read 24 bytes from the input. The string `id` for `/bin/sh` should come after input for `scanf()`. The `/bin/sh` will get the `id` and run it. You can read the flag in the same way.

Now, someone may want to get a interactive shell. It's very clever to run `(python -c 'print "A"*20 + "\xef\xbe\xad\xde"'; cat) | /narnia/narnia0`. The `cat` will read string from the `STDIN`, and send it by the pipe to `/bin/sh`, which is executed by the `narnia0`.
## Exploit Example
[Here](https://github.com/JayvicWen/CTF/tree/master/Wargames/OverTheWire/Narnia/level0) is a example of exploit script which is full automated from ssh connection to flag capturing. You just need to run the `solve.py` with proper dependency(pwntools) installed.