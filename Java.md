Difference of HashMap vs Treemap vs LinkedHashMap
-----
Treemap: keys are sorted

http://www.programcreek.com/2013/03/hashmap-vs-treemap-vs-hashtable-vs-linkedhashmap/]

HashMap methods
http://www.programcreek.com/2013/04/frequently-used-methods-of-java-hashmap/

#String formatting
sb.append(String.format("%.3f\n",ans));

#注意comparator for long types
return l1 -l2 --> doesn't work, should be like below
	if (l1>l2)
		return 1;
	if (l1<l2)
		return -1;
	return 0;