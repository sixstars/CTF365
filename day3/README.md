# Day 3

## Challenge 
Basic overflow

## Category
Exploit

## Description
This challenge is for the ones that want to learn basic exploitation.

```bash
ssh narnia0@narnia.labs.overthewire.org
```
The password is the same as username.

You should run the program `/narnia/narnia0` and try to get the shell of user `narnia1`.
The flag is in `/etc/narnia_pass/narnia1`.
[This file](./narnia0) is just a copy of `/narnia/narnia0` on remote server.
You may run it on your own Linux machine.

In order make it easier for you to spot the vuln and abuse it, we give you the [source code](./narnia0.c).

> As this problem may have some unexpected gaps.
> I give you a simplified one which contains only the original knowledge point.
> You can try it first.
>
> This is the [source code](./simplified.c).
> Because our server is not ready yet, we just compile it for you.
> You may need to run it on your own machine.
> Here is the [excutable](./simplified) Try to get a shell!

## Hint
Do not have any idea?
Maybe you can take a look at this [hint](./HINT.md).

## Credit
<http://overthewire.org/wargames/narnia/narnia0.html>
