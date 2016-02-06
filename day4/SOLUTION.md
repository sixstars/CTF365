# Day4
## Solution
This problem is a classical substitution cipher, in which each character is replaced by another one. Since it's a one-to-one mapping, the cipher keeps the frequency of each character unchanged. With the frequency table of English and the large enough cipher text, it's easy to crack this simple cipher system.

[Hint2](./HINT2.md) gives the solution directly, but if you dislike its encapsulation on problem-solving, [here](https://github.com/ctfs/write-ups-2014/blob/master/plaid-ctf-2014/twenty/cipher_solver.py) is another open-source automatic tool. It randomly generates a replacement table and score the decrypted text with 4-gram frequency.
