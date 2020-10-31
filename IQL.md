Nice queries.

#between, OR

from index 2017-01-01 2017-01-02
where lucene("!number:[10 TO 20]")
group by number 

from index 2017-01-01 2017-01-02
where not(between(number, 10, 20))
group by number

from index 2017-01-01 2017-01-02
where ((number<10)+(number>=20))>0
group by number

#empty|null string|int
HASSTRFIELD(column)=0
HASINTFIELD(field)>0

#where
field=~'(word.*)|(.* word.*)' field!=~'aword'

#group by time(1d)

#IQL v1.
> AND
((value<=3000) +(value>=0))>1

> OR 
(columnA = "A" + columnB < B) > 0

 