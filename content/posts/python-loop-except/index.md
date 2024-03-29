+++
title = "Python for loops have an else clause"
author = ["Alexander Neumann"]
date = 2022-09-22T00:00:00+02:00
lastmod = 2022-09-23T00:44:51+02:00
tags = ["python"]
draft = false
weight = 2001
[cover]
  image = "unsplash-code.jpg"
  caption = "Photo by [Chris Ried](https://unsplash.com/@cdr6934) on Unsplash.com"
  responsiveImages = true
+++

<div class="skipRender">

{{< figure src="unsplash-code.jpg" >}}

</div>

Something that is not common knowledge is the fact that Python for loop can have an `else` clause.
An else clause is executed when a for loop ends normally without break being called.
Internally, Python will trigger a `StopIteration` when this happens.

```python
def check(target, iterable):
    for element in iterable:
        if element == target:
            print("Jup, target is in container.")
            break
    else:
        print("Seems like target is not in container.")

check("s", "a string")
# >>> Jup, target is in container.
check("e", "a string")
# >>> Seems like target is not in container.
```

Such an else clause may save you some lines of codes when itterating in the middle of a complex function by getting rid of assignment checks or boolean flags.
However, in the simplified example above using `return` instead of `break` and `else` would most likely produce code that is more robust and easier to comprehend as `for/else` is not a well-known construct.