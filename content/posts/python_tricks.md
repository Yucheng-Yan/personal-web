---
author: ["Yucheng Yan"]
title: "Python Tricks"
date: "2026-05-11"
description: "Some python tricks that I didn't know existed or how to use before."
summary: "Some python tricks that I didn't know existed or how to use before."
tags: ["python"]
categories: ["articles"]
series: []
ShowToc: false
TocOpen: true
social:
  fediverse_creator: "@yc_yan@hachyderm.io"
---

### Using casting functions to determine the datatype of a token
When you implement a parser, it is very likely that you need to figure out what type your token is.

When you try to determine if the token is an integer, instead of using `isdigit()`, consider using a `try / except` block with casting functions like:

```python
def is_integer(token):
    try:
        int(token)
        return True
    except ValueError:
        return False
```

Why? When the token is a negative number, `isdigit()` does not consider it an integer and returns `False`.

```
>>> '-1'.isdigit()
False
>>> int('-1')
-1
```