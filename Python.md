#Sort a dictionary by value
sorted_myDic = sorted(myDic.items(), key=operator.itemgetter(1), reverse = True)

#ElasticSearch
Read: http://marcobonzanini.com/2015/02/02/how-to-query-elasticsearch-with-python/
Done: Installed ipython, jupyter-notebook
http://blog.tryolabs.com/2015/02/17/python-elasticsearch-first-steps/



#RESTful API: 
from elasticsearch import Elasticsearch
es = Elasticsearch([{'host': host, 'port': port}])
> elasticsearch
	index, create, delete, and update
	es.search(index=_index, doc_type=_type, body={})
>Indices
	es.indices.create(index=_index, body={})
	es.indices.put_settings(index=_index, body={})
	es.indices.analyze(index=_index,body=text, params={})


#linebreak in code
x = "sa \
	asda "

#iterate with index through list
for idx, val in enumerate(ints):
    print idx, val


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

#String formatting
x = "%03d %03d" % (1,10)



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
