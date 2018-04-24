#Sort a dictionary by value
sorted_myDic = sorted(myDic.items(), key=operator.itemgetter(1), reverse = True)

#ElasticSearch
Read: http://marcobonzanini.com/2015/02/02/how-to-query-elasticsearch-with-python/
Done: Installed ipython, jupyter-notebook
http://blog.tryolabs.com/2015/02/17/python-elasticsearch-first-steps/

#Jupyter notebook
To install:
pip3 install jupyter
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

#see current folder pwd
import os
cwd = os.getcwd()    


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

#Escape % in print
s = "%s 55%% %s" %(1,2)

#StringFormatting
'item{} -> "Step{}"'.format(i, j)

#Download image url
import os
import requests
import shutil

if not os.path.isfile(path):
        r = requests.get(url, stream=True)
        if r.status_code == 200:
            with open(path, 'wb') as f:
                r.raw.decode_content = True
                shutil.copyfileobj(r.raw, f)

PS: Path must be absolute

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
re.sub(r'([^0-9])',"",url) #replace all except digits
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
with open('filename') as f:
    lines = f.readlines()

with open("file.txt", "r") as ins:
    array = []
    for line in ins:
        array.append(line)    

#write to file
f= open("greet.txt","w+")
  f.write("Hello: %s\n" % ("World"))
f.close()

#Write srt file: subtitlte
f= open("file.srt","w+")
for i in range(30):
  #Required
  f.write("%d\n" %i)
  f.write("00:00:%02d,00 --> 00:00:%02d,00\n" % (i, i+1))
  f.write("Hello it is sec: %d\n\n" % i)
f.close()


#pwd, cwd, working directory
import os
cwd = os.getcwd()


#Globally Unique User Identifier GUUID
import uuid
Use -> uuid4()    

#DateTime
from datetime import date
import datetime
today = date.today()
ymonth = str(today.year) + str("%02d" % today.month)
"From {fromDate}".format(fromDate =str(today))
toukago = today + datetime.timedelta(days=10)
> date to str
    print today.strftime('%Y-%m-%d')
> str to date
    datetime.datetime.strptime('24052010', "%d%m%Y").date()

#Get epoch time directly from date object
today = datetime.date.today()
int(time.mktime(today.timetuple()))

#eval
ThreeInOne = lambda a, o, s: eval("sum(a)/len(a)%ss"%o)

#short
Zeros =f= lambda n:n and n/5+f(n/5)

#global variable
if defined in a function make it global even it is a parent function.

#Subprocess
`subprocess.call(args, *, stdin=None, stdout=None, stderr=None, shell=False)`
we can direct stdout, stderr only to file. So we can not use it in the program. 
If there is a space in command of args, make `shell=True`. (For Trusted Input)

subprocess.Popen(args, bufsize=0, executable=None, stdin=None, stdout=None, stderr=None, preexec_fn=None, close_fds=False, shell=False, cwd=None, env=None, universal_newlines=False, startupinfo=None, creationflags=0)

We can pipe stdout, stderr into stream.

#try catch any error
try:
    something()
except:
    fallback()

#Numpy
Remove None types from numpy array
a[a != np.array(None)]


#Exit program
import sys
sys.exit(0)

#unicode, mysql escape
check file encoding!

#escape %
%%


#Redefining funtion
def Blindfolded(s, n, i=0):
    if n <= s:
        return [0, n - 1]
    b = Blindfolded(s - i/2, n - s + 1, i%2 + 1)
    return [b[1], s - b[0] - 1]

#Accessing to mysql db
http://www.tutorialspoint.com/python/python_database_access.html

> 
```python
#!/usr/bin/python
import MySQLdb
# Open database connection
db = MySQLdb.connect("localhost","testuser","test123","TESTDB" )
# prepare a cursor object using cursor() method
cursor = db.cursor()
# Prepare SQL query to INSERT a record into the database.
sql = "SELECT * FROM EMPLOYEE WHERE INCOME > '%d'" % (1000)
try:
   # Execute the SQL command
   cursor.execute(sql)
   # Fetch all the rows in a list of lists.
   results = cursor.fetchall()
   for row in results:
      fname = row[0]
      lname = row[1]
      age = row[2]
      sex = row[3]
      income = row[4]
      # Now print fetched result
      print "fname=%s,lname=%s,age=%d,sex=%s,income=%d" % \
             (fname, lname, age, sex, income )
except:
   print "Error: unable to fecth data"
#cursor execute
cursor.execute("%s %s" % (a, b))
cursor.execute("%s %s", [a, b])
cursor.execute("%s", (a,) )
% , needed if there is only one column
# disconnect from server
db.close()
```


#Related to pip
`chown -R user:group ~`
Six is installed to system so we can't uninstall.
`sudo -H pip install pp --ignore-installed`

#cursor last query executed
cursor._last_executed

#Work on virtual environment
First, install virtualenvwrapper by pip.
[Useful link](https://www.sitepoint.com/virtual-environments-python-made-easy/)
virtualenvwrapper | to see help message
mkvirtualenv new-env
workon my-env
deactivate
rmvirtualenv old-env

#Install different version for python
Most of the error is due to permission related to sudo
It's better and easier to use virtualenv.
Basically we install python with different version in local folder. And we install pip and virtualenv to our new python.
Finally, we create virtualenv for our version of python.
[Here](http://stackoverflow.com/questions/5506110/is-it-possible-to-install-another-version-of-python-to-virtualenv)

PS: Be careful with version numbers when downloading tar source file.
```
For Python 2.7.1
1) Get Python source
mkdir ~/src
mkdir ~/.localpython
cd ~/src
wget http://www.python.org/ftp/python/2.7.1/Python-2.7.1.tgz
tar -zxvf Python-2.7.1.tgz
cd Python-2.7.1

make clean
./configure --prefix=/home/${USER}/.localpython
make
make install
2) Install virtualenv
virtualenv source

cd ~/src
wget http://pypi.python.org/packages/source/v/virtualenv/virtualenv-1.5.2.tar.gz#md5=fbcefbd8520bb64bc24a560c6019a73c
tar -zxvf virtualenv-1.5.2.tar.gz
cd virtualenv-1.5.2/
~/.localpython/bin/python setup.py install
3) Create a virtualenv using your local python
virtualenv docs

mkdir /home/${USER}/virtualenvs
cd /home/${USER}/virtualenvs
~/.localpython/bin/virtualenv py2.7 --python=/home/${USER}/.localpython/bin/python2.7
4) Activate the environment

cd ~/virtualenvs/py2.7/bin
source ./activate
5) Check

(py2.7)$ python
Python 2.7.1 (r271:86832, Mar 31 2011, 15:31:37) 
[GCC 4.4.5] on linux2
Type "help", "copyright", "credits" or "license" for more information.
>>> exit()

(py2.7)$ deactivate
$ python
Python 2.6.6 (r266:84292, Sep 15 2010, 15:52:39) 
[GCC 4.4.5] on linux2
Type "help", "copyright", "credits" or "license" for more information.
```

#Read excel & INSERT MANY
df =pd.read_excel('file.xlsx', header=1)
values = df.values
columns = df.columns
qlist = []
for row in values:
  rlist = []
  rlist.append(('id', row[0]))
  rlist.append(('name', row[4]))
  d = dict(rlist)
  qlist.append(d)
query="""
 INSERT INTO table (id, name)
 VALUES (%(id)s, %(name)s)
"""
cursor.executemany(query, qlist)


#MYSQLDB
pip install mysqldb
`No matching distribution found for MySQLdb`
--> pip install MySQL-python
`EnvironmentError: mysql_config not found`
-->export PATH=$PATH:/usr/local/mysql/bin
-->export PATH=$PATH:/Applications/MAMP/Library/bin (for MAMP)

#Beautiful soup
> 
Install
    pip install beautifulsoup4
import
    from bs4 import BeautifulSoup
Usage
    html = urllib2.urlopen("http://example.com")
    soup = BeautifulSoup(html)
  OR 
    html = """
    <html>
    ...
    </html>
    """

    src = soup.p.img['src']
    all_a = soup.find_all("a")
  Attrib
    soup.a.get("href")
    soup.find_all(class_="link", href="/link")
    soup.find_all(attrs={"class": "link", "href": "/link"})

    import re
    soup.find_all(re.compile("^b"))

[Documentation](https://www.crummy.com/software/BeautifulSoup/bs3/documentation.html#The%20attributes%20of%20Tags)
[Good link](http://qiita.com/itkr/items/513318a9b5b92bd56185)

#XMLparse
[Qiita](http://hikm.hatenablog.com/entry/20090206/1233950923)
[Tutorial](http://lxml.de/tutorial.html)
> Install
  Built-in
import
  import xml.etree.cElementTree as ET
Usage
    tree = ET.ElementTree(file=urllib2.urlopen('https://doda.jp/careercompass/feed'))
    root = tree.getroot()  
  OR
    xmlString = '<window width="1920"><title font="large" color="red">sample</title><buttonbox><button>OK</button><button>Cancel</button></buttonbox></window>'
    root = fromstring(xmlString)
>
    root[i]
    root.get("name")
    root.tag
    root.text
    ET.SubElement(root, "channel")

  items = root.findall("channel/item")
  for item in items:
    url = item.find("link").text
    html = item.find("description")
    soup = BeautifulSoup(html.text, "html.parser")
    print soup.p.img['src']
> 
    print item.tag
    # attributeの取得
    print item.get("width")
    # デフォルトを指定してattributeを取得
    print item.get("height", "1200")
    # attribute名のリスト取得
    print item.keys()
    # (attribute, value)形式タプルのリスト取得
    print item.items()


#singularize, pluralize
from nltk.stem import WordNetLemmatizer

wnl = WordNetLemmatizer()

def isplural(word):
    lemma = wnl.lemmatize(word, 'n')
    plural = True if word is not lemma else False
    return plural, lemma

nounls = ['geese', 'mice', 'bars', 'foos', 'foo', 
                'families', 'family', 'dog', 'dogs']

for nn in nounls:
    isp, lemma = isplural(nn)
    print nn, lemma, isp

#Unicode related
x = u"名詞"
print x
--> always prints BL>;l
--> Reason : might be sth to do with encoding.
Try copy the contents to new file


#Pand excel float precision
> !! formatting 2ланд нь бичихгүй бол гарахгүй байв.

xf = pd.DataFrame(values)
writer=pd.ExcelWriter(path + 'result.xlsx', engine='xlsxwriter')
xf.to_excel(writer, sheet_name='Sheet1', index=False, header=columns, float_format='%.2f')
workbook = writer.book
worksheet = writer.sheets['Sheet1']
rate=workbook.add_format({'num_format': '0.00 '})
worksheet.set_column('B:F', None, rate)
writer.save()

> Simple version (xls)
    ef=pd.DataFrame(values)
    ef.to_excel(path + 'result.xlsx', index=False, header=columns, encoding='utf8', float_format='%.3f')
>Simple version (csv)
    cf=pd.DataFrame(values)
    cf.to_csv(path + 'result.csv', index=False, header=columns, encoding='utf8', decimal=',', sep=' ', flo    at_format='{:.2f}')

#igraph Macport
install port for cairo
install cairo
pip install cairocffi

#igraph brew
Go to homebrew: brew.sh, and install brew for Mac. Then,

brew install cairo
brew install py2cairo
brew install igraph — install C-core
sudo pip install python-igraph —install igraph for python
+ pip install cairocffi


export PYTHONPATH=/Users/me/.virtualenvs/my-env/bin/python$PYTHONPATH
したら出た！
→brewのpy2cairo（かigraph）は自分のpythonに対してやっていたと思われる


#Set from list
lst = ['bab' , 'abc', 'cab']
for word in lst:
  anag.append(''.join(sorted(list)))
s = set(anag)

#Inline filter
[ EXP for x in seq if COND ]

#virtualenv problems
> Check printenv

pip install -I package 
pip list