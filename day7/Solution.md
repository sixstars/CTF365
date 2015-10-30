# Day7
## Solution
Use WinHex or 010 Editor (on Windows), xxd or 010 Editor on OS X or Unix, to inspect the hex dump of the jpeg file.

You can see a string of zeros and ones at the end of this file. You should know that it's OK to attach any information to the end of a jpg/png file without causing any side effect when showing the image.

However, an extra step is necessary to turn the string into a flag.

We know an ASCII character consists of 7 bits, and (perhaps) an extra leading 0. So we can divide these zeros and ones into several groups, with each group containing 7 or 8 bits. Then, restore characters from these grouped bits, and you can get a readable string. It's the flag we want.
