python-igraph
=======

from igraph import *
karate = Nexus.get("karate")
dend = karate.community_fastgreedy()
k=2
cluster = dend.as_clustering(k)
members = cluster.membership


dend: outputs full dendogram
cluster: best clustering (k can be null)