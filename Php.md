PHP

#formatting float
echo number_format($num, 2, ".");

#Date format・Addition
$myDate = date("Y-m-d", strtotime(myDate . ' +1 day'));

$d = "2012-01-31";
$a = strtotime($d);
$a = strtotime( "+1 day", $a );
echo date("Y-m-d",$a);

http://takuya-1st.hatenablog.jp/entry/20120419/1334825878


#Sorting array of object with custom function
usort($your_data, function($a, $b)
{
    return strcmp($a->name, $b->name);
});