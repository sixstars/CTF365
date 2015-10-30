# Day4
## Solution
As you can guess, this problem is a classical substitution cipher, in which each character is replaced by another one. Since it's a one-to-one mapping, this cipher keeps the frequency of each character unchanged. With a frequency table for English and large enough cipher text, it's easy to crack this simple cipher system.

[Hint2](./Hint2.md) has already given the solution directly, but if you dislike its encapsulation on problem-solving, [here](https://github.com/ctfs/write-ups-2014/blob/master/plaid-ctf-2014/twenty/cipher_solver.py) is another automatic tool with source code open. It randomly generates a replacement table and score the decrypted text with 4-gram frequency.
