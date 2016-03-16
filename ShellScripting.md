#variable
NO space around=
month=$(date +%m)
year=$(date +%Y)

line1="cd ~/"
line2="python a.py $month > ~/out.txt"
line3="python b.py > ~/out_$year$month.txt"
echo -e "$line1\n$line2\n$line3" > out.sh

#Substract date
p=$(date "--date=$(date) -60 day" +%Y-%m-%d)

yes=$(date -d "4 day ago 13:00 " '+%Y-%m-%d %H:%M:%S')

#execute string in shell
eval $cmd

#array

array=( "A" "B" "ElementC" "ElementE" )
for element in ${array[@]}
do
    echo $element
done

echo ""
echo "Nbr of elements:" ${#array[@]}

echo ""
echo ${array[@]}
