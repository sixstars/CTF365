# Day 3
## Solution - `simplified`
As you can see, the length of array `buf` is 20, while `scanf()` accept a input string with length 21. So you can directly do the overflow with input `AAAAAAAAAAAAAAAAAAAAW`.
## Solution - `narnia0`
It's nearly same as `simplified`. However, you should input some special characters, which situation you will always meet in exploition.

The usual way is using Python to output it. Don't forget the endian issue. So you can get the input string with Python script `print 'A'*20+'\xef\xbe\xad\xde'`

But you will find that you don't get a shell from the program. Why? Because the bash add an `EOF` at the end of the string which python output. Although the program executes the `/bin/sh`, getting an `EOF` will end the shell. So, if you want to send a command to the program to execute in `/bin/sh`, you can run `(python -c 'print "A"*20 + "\xef\xbe\xad\xde"'; echo "id") | /narnia/narnia0`. Don't use `(python -c 'print "A"*20 + "\xef\xbe\xad\xdeid"')` because the `scanf()` just read 24 bytes from the input. The string `id` for `/bin/sh` should come after input for `scanf()`. The `/bin/sh` will get the `id` and run it. You can read the flag in the same way.

Now, someone may want to get a interactive shell. It's very clever to run `(python -c 'print "A"*20 + "\xef\xbe\xad\xde"'; cat) | /narnia/narnia0`. The `cat` will read string from the `STDIN`, and send it by the pipe to `/bin/sh`, which is executed by the `narnia0`.
