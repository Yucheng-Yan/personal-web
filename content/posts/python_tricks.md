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

To do this, simply use a `try / except` block with casting functions like:

```python
def is_integer(token):
    try:
        int(token)
        return True
    except ValueError:
        return False
```
