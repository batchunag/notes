#Sort a dictionary by value
sorted_myDic = sorted(myDic.items(), key=operator.itemgetter(1), reverse = True)

#ElasticSearch
Read: http://marcobonzanini.com/2015/02/02/how-to-query-elasticsearch-with-python/
Done: Installed ipython, jupyter-notebook
http://blog.tryolabs.com/2015/02/17/python-elasticsearch-first-steps/

#Jupyter notebook
To run:
jupyter notebook --NotebookApp.port=8754

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

Remember to convert each element of the array to string before join.

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

#int to binary
"{0:b}".format(10)
bin(6)[2:]

#operators
a = [1,9,12]
print sum(a)
sublist = a[:2]

reduce(lambda x, y: x+y, [1, 2, 3, 4, 5])

#REGEX
```python
re.sub("\d","#",str) #replaces every digit by #
```

#sort
>>> a = 'ZENOVW'
>>> ''.join(sorted(a))
'ENOVWZ'

# short if
return ["No","Yes"][c(n,m)]

#Set union and intersection
You can use | for set union and & for set intersection.

#Make string mutable (convert into array)
t = [c for c in s]

#Sort string
y = sorted(x)

#Read from file
fo = open("foo.txt", "wb")
print "Name of the file: ", fo.name
print "Closed or not : ", fo.closed

#DateTime
from datetime import date
today = date.today()
ymonth = str(today.year) + str("%02d" % today.month)
"From {fromDate}".format(fromDate =str(today))

