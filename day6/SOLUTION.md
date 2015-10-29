# Day 6

## Solution

Below is the source code:

```c
#include <stdio.h>
#include <string.h>

char buf[33] = {};

int main() {
    char raw_buf[33];
    printf("Input your key: ");
    scanf("%32s", raw_buf);
    for (int i = 0; i < 32; ++i) {
        buf[i] = raw_buf[i] ^ 6;
    }
    if (strcmp(buf, "kquavkbeapakcxgwgdhhodwdknbjpttj") == 0) {
        printf("The flag is *ctf{%s}\n", raw_buf);
    } else {
        printf("Invalid key!\n");
    }
    return 0;
}
```

In most cases, you don't have the original source code, so you have to do the reverse engineering. Use IDA to open the binary program, locate the main function, use F5 to get decompiled source code, and read the code. You can find that the decompiled source code looks similar to the original source code.
I think I need to say nothing more (>_>).

> As we provide an `.exe` for Windows, some of you might have tried to reverse it and got into trouble.
> So I decide to give some extra explanations for it.
> 
> Originally I'd like to compile the program with MinGW in 32 bits mode. However, because of an incident, we compiled it with VS in 64 bits mode. 
> So the program is expanded with some extra useless code. It makes this challege more complex.
> 
> In order to solve it, you'd better find the useful strings first, such as `Input your key` and `Invalid key` (strings view in IDA / search strings in OllyDebug).
> Then you can use cross-reference (shortcut key `x`) in IDA to find the main function. In OllyDebug, you can add a memory breakpoint, too.
