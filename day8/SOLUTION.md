# Day8
## Solution
You can see in this public key, the `e` is nearly as large as `n`. If you google with something like "RSA with large e", you will find one interesting thing called [Wiener's attack](https://en.wikipedia.org/wiki/Wiener's_attack).

Since there are so many scripts in Github, you don't even need to write it yourself. You can download one and calculate the factors for `n`, using it to recover the plain text.