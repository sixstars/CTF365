# Day 12
## Solution
In fact, this challenge is not difficult, but maybe complex.

Firstly, just treat the picture as a `zip` file (you can either change the extension or not). Unzip it (the password is `******`), and you'll get 64 images.

Among the images, 56 of them are broken QR codes. You need to fix them before scanning them. (Don't know how? Just copy the bottom left rectangle shape, paste it to the top left corner and keep it neat.) The other 8 images are bar codes. Scan the bar codes, you'll get numbers between 0-55 which are filenames of the QR codes that are useful. Scan the correct QR codes and base64-decode the texts. (Don't know why you should base64-decode the texts? Because some of them have `=` at the end. This is a characteristic of base64-decoded texts.)

Finally, join the words you get to compose a meaningful sentence which is the flag. You need to omit white spaces at submission.
