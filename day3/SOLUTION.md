# Day 3
## Pre knowledge
To solve this challange, you need to know the structure of a stack.
If you don't know what is a stack, just google it.

Almost all parameters of a function call and local variables in a function are saved on the stack.
The order of parameters on a stack is decided by the order you write the parameters in the program and the rules of function call.
The order of local variables is decided by the order you define the local variables in a function and compilation parameters.

When we compile the program with certain parameters, the variable `val` is located immediately after the array variable `buf`. While `C/C++` do not check the legitimacy of index when access an element of an array, you can access `val` by `buf[20]` in these two programs.
## Solution - `simplified`
As you can see, the length of the array `buf` is 20, while `scanf()` accept an input string with length 21. So you can directly do the overflow with input `AAAAAAAAAAAAAAAAAAAAW`.
## Solution - `narnia0`
It's nearly the same as `simplified`. However, you should input some special characters, which is usual in exploitions.

The usual way is to use Python to generate special characters. Don't forget the endian issue! So you can generate the input string with Python script `print 'A'*20+'\xef\xbe\xad\xde'`

But you will find that you don't get a shell from the program. Why? Because `bash` (your default shell) adds an `EOF` at the end of the string which python outputs. Although the program executes the `/bin/sh`, getting an `EOF` will end the shell. So, if you want to execute something in `/bin/sh`, you can run `(python -c 'print "A"*20 + "\xef\xbe\xad\xde"'; echo "id") | /narnia/narnia0`. Don't know what `|` does? Just Google `Unix pipe`. Don't use `(python -c 'print "A"*20 + "\xef\xbe\xad\xdeid"')` because the `scanf()` just reads 24 bytes from the input. The string `id` for `/bin/sh` should come after the input for `scanf()`. The `/bin/sh` will get the `id` and run it. You can read the flag in the same way, using `cat`.
Now, you may want to get an interactive shell. It's very clever to run `(python -c 'print "A"*20 + "\xef\xbe\xad\xde"'; cat) | /narnia/narnia0`. The `cat` will try to read strings from `STDIN`, and send it through the pipe to `/bin/sh`, which is executed after you overflow `narnia0`.
## Exploit Example
[Here](https://github.com/JayvicWen/CTF/tree/master/Wargames/OverTheWire/Narnia/level0) is an exploitation script which is fully automated, from ssh connection to flag capturing. You just need to run the `solve.py` with proper dependency (pwntools) installed.
