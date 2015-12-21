


Notes
---
> Any directory with an __init__.py file is considered a Python package

> This and other issues led to the idea that using stateless functions is a better programming paradigm.

> it may be a good discipline to avoid assigning to a variable more than once

> Create a concatenated string from 0 to 19 (e.g. "012..1819")

```python
# Bad

nums = ""
for n in range(20):
  nums += str(n)   # slow and inefficient
print nums

#Good

nums = []
for n in range(20):
  nums.append(str(n))
print "".join(nums)  # much more efficient

#Best

nums = [str(n) for n in range(20)]
print "".join(nums)
```

Q & A
----



Not answered
---
> 
Once modu.py is found, the Python interpreter will execute the module in an isolated scope. Any top-level statement in modu.py will be executed, including other imports if any.

> ??

```python
def foo():
    # do something

def decorator(func):
    # manipulate func
    return func

foo = decorator(foo)  # Manually decorate

@decorator
def bar():
    # Do something
# bar() is decorated
```

> Really?

```python
my_list = [1, 2, 3]
my_list[0] = 4
print my_list  # [4, 2, 3] <- The same list as changed

x = 6
x = x + 1  # The new x is another object
```

> need to verify

```python
foo = 'foo'
bar = 'bar'

foobar = '%s%s' % (foo, bar) # It is OK
foobar = '{0}{1}'.format(foo, bar) # It is better
foobar = '{foo}{bar}'.format(foo=foo, bar=bar) # It is best
```