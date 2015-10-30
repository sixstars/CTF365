# Day10
## Solution
In fact, this challenge is not complex, although the program includes a really complex function.

We use this challenge to tell you that once you find the right way, some problems may become really easy. So do not feel afraid.

If we pass the complex function (which we call it `unknown_function`), we'll see that the logic of this program is:

```cpp
if (input_string == unknown_function(CONSTANT_STRING)) {
    cout << "Right!" << endl;
}
```

So, it's obvious that once put a break point after the `unknown_function` has been called and run, we can get the string we need to input.

Don't you think it's really simple?
