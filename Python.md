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