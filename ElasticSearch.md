Text Search

#Open Source
Kibana : Visualize
Elasticsearch: Data store, search, analyze
Logstash : Collect, parse

#Commercial
Elastic as a service

#Basics
Just run 
```./bin/elasticsearch ```

```localhost:9200/_cluster/health?pretty``` 
to check the status.


#kuromoji
http://qiita.com/dos_shiitake/items/38d8b3b2977e478ad93c
``` .bin/plugin -install elasticsearch/elasticsearch-analysis-kuromoji/2.3.0 ```

#Marvel
http://localhost:9200/_plugin/marvel/kibana/index.html
http://localhost:9200/_plugin/marvel/sense/index.html

#Easy Reference
http://okfnlabs.org/blog/2013/07/01/elasticsearch-query-tutorial.html

#Cheat Sheet
http://elasticsearch-cheatsheet.jolicode.com/#goto_title_3

#Script in ES
	POST /website/blog/1/_update
    {
       "script" : "ctx._source.views+=1"
    }

#Aggregation
search_type = "count" is faster because we skip the fetching phase