#for loop
for i in {1..99..2}
do
    echo $i;
done

for ((i=1; i<=99; i+=2))
do
    echo $i;
done

#incremenet
	((s+=x))
    c=$(( $c+1 ))

#float division
	echo "scale=3; $s / $n " | bc;

#cut functions
cut -f-3 -d $'\t' a.txt
cut -c1,2,4- -d ":" b.txt

[Youtube videos](https://www.youtube.com/user/JtheLinuxguy/playlists)

#head & tail
-c10, -n20, -b50
#translate
echo 'Hello ' | tr 'elo' 'ai'
tr -d [a-z]
tr -d [0-9]
tr -s [:space:] ' '
>	Remove all except digits
echo "my username is 432234" | tr -cd [:digit:]

#sort
sort -n -r
Reverse numbers

#sed
echo 'Height: 1000 centimeters' | sed 's/\([0-9]*\)centimeters/\1cm/g'
sed -e 'command1' -e 'command2' data.txt
sed '2,$ s/alpha/beta/i' data.txt
sed '/startPattern/,/endPattern/ s/alpha/beta/i' data.txt
echo 'hello world' | sed 'y/eod/EOD/'
> Find string with specific regex pattern
echo 'first url,&second=123& third url&asdas' | sed 's/.*\&\(second=[^\&]*\)\&.*/\1/'

