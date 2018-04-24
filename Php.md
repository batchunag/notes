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

#Array intersection
$intersection = array_intersection($a, $b);
#Array union
$union = array_unique(array_merge($a, $b));

#Get random number
below is better than rand();
mt_rand() / mt_getrandmax();

#install on nginx
http://todsul.com/tech/install-and-configure-php-fpm-on-nginx/
http://qiita.com/tukiyo3/items/b1d29a257c41d97d6107

#string functions
strlen(s)
strstr(s): index of substring
