Nice queries.

#between, OR
https://go.indeed.com/IQLC4NN2W

from index 2017-01-01 2017-01-02
where lucene("!number:[10 TO 20]")
group by number 

from index 2017-01-01 2017-01-02
where not(between(number, 10, 20))
group by number

from index 2017-01-01 2017-01-02
where ((number<10)+(number>=20))>0
group by number


#where
field=~'(word.*)|(.* word.*)' field!=~'aword'

#group by time(1d)

#IQL v1.
> AND
((value<=3000) +(value>=0))>1

> OR 
(columnA = "A" + columnB < B) > 0

 