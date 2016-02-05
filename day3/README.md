# Day 3

## Challenge
Basic overflow

## Category
Exploit

## Description
This challenge is for the ones that want to learn basic exploitation.

What is exploitatation? The challenge requires that you exploit (make use of) bugs of a program to get access to a system. Don't worry, it's just a game, because bugs are intentionally designed by the challenge designer and your access to the system is limited. In most challenges, you will overflow a remote program to get a shell access. Finally, you use the shell to get a flag to prove that your exploitation is successful. 

Execute the following command in your terminal:

```bash
ssh narnia0@narnia.labs.overthewire.org
```
The password is the same as the username. Now, you are user `narnia0` on that machine. Your aim is to become user `narnia1` on that machine to get the flag. To do this, you should run the program `/narnia/narnia0` and try to get the shell of user `narnia1`. After that, since the flag is in `/etc/narnia_pass/narnia1`, you should run ```cat /etc/narnia_pass/narnia1``` to get the flag.

The general way of finishing the challenge is to first run the program on your own machine, because the network may be slow. [This file](./narnia0) is just a copy of `/narnia/narnia0` on the remote host. You may run it on your own Linux machine. Ubuntu is recommended. After you get a shell on your own machine, you should use the same method to get a shell on the remote host and get the flag. Confused? Please remember that exploiting your own machine is just an experiment. You learn and play the program to find the way of exploitation. After you find the right way, you exploit the remote host and get the flag.

In order to make it easier for you to locate the vulnerability/bug and abuse/exploit it, we give you the [source code](./narnia0.c).

> As this problem may be hard for beginners,
> we give you a simplified one which contains only the most basic knowledge point.
> You can try it first on your own machine.
>
> This is the [source code](./simplified.c).
> Because our server is not ready yet, you will not have a chance to exploit the remote host. We have compiled the simplified program for you.
> You need to run it on your own machine.
> Here is the [executable](./simplified). Try to get a shell on your own machine and you finish the game. Note that you can only get the flag if you finish the narnia0 challenge. If you feel the narnia0 challenge is too complicated, you can just finish the simplified challenge on your own machine and goto the next challenge.

## Hint
No idea?
Maybe you can take a look at this [hint](./HINT.md).

## Credit
<http://overthewire.org/wargames/narnia/narnia0.html>
