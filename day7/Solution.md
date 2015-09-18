# Day7 Solution

Use winhex or 010editor(on windows), xxd or 010editor on unix, to inspect hex dump of this jpeg file.

You can see a 01 string at the end of this file. As we know it's free to attach any information to the end of a jpg/png file without causing side effect when show image.

There is an extra step to turn it into a flag.

We know an ascii char consist of 7 bits with a suffix 0. So we can divide these 0/1 into several groups, with each group containing 7 or 8 bits. Then restore char from these grouped bits, you can get a readable string, it's flag we want.
