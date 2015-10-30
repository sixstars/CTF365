# Day8
## Solution
You can see in this public key that the `e` is nearly the same size as `n`. If you google something like "RSA with large e", you will find one interesting thing called [Wiener's attack](https://en.wikipedia.org/wiki/Wiener's_attack).

Since there are so many scripts in Github, you don't even need to write the cracking script by yourself. You can download an implementation and calculate the factors for `n`, and use it to recover the plain text.
