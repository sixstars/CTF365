# Day 11

## Solution
In fact, this challenge is really easy.
As mentioned in hint, you can try base64, base32, base16. And finally, you'll find that you can decode it with:

```python
import base64
cypher_text = 'R1EyRE1SUlNHQTNUU05TR0c0MlRFTUJXSUkzRUtOU0dHNDNURU1CWEdRM0RRTlJWR0lZRE9NWldHVTNER05aU0dZMlRPTkJTR0EzRU1OUldHSVlET01aV0hFM1RRTlpURzQyRE1NSlhHSTNUR00yRw'
print base64.b16decode(base64.b32decode(base64.b64decode(cypher_text + '==')))
```

Pay attention to the `==` appended to the cypher text. In base64, trailing equal signs are just placeholder for alignment and can be omitted. So we do this as a tricky.

When you get the plain text, the only thing you can do is putting it in search engine.
And in fact, you will never get the flag if you use **Baidu**. We only allow the page with flag to be indexed with GoogleBot.
We do this just want to notice you that `Baidu` is really a terrible search engine especially in CTFs. **You will suffer a lot if you insist to use it**.