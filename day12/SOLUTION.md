# Day12

In fact, this challenge is not difficult, but maybe complex.

Firstly, just treat the picture as a `zip` file (you can whether change the extension or not). Unzip it (password is just `******`), you'll get 64 images.

Among the images, 56 of them are broken QR codes (you need to fix them in order to scan) and 8 are bar codes. Scan the bar codes, you'll get numbers between 0-55 which are the ids of QR codes that are useful. Scan the correct QR codes and base64 decode the text.

Finally, join the words you get to compose a meaningful sentence which is flag (You need to omit white spaces when submit).
