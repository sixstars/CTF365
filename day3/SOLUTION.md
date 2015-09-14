# Day 3
## Solution - `simplified`
As you can see, the length of array `buf` is 20, while `scanf()` accept a input string with length 21. So you can directly do the overflow with input `AAAAAAAAAAAAAAAAAAAAW`.
## Solution - `narnia0`
It's nearly same as `simplified`. However, you should input some special characters, which situation you will always meet in exploition.

The usual way is using Python to output it. Don't forget the endian issue. So you can get the input string with Python script `print 'A'*20+'\xef\xbe\xad\xde'`

TODO eof issue