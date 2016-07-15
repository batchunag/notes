#Install composer globally
https://getcomposer.org/doc/00-intro.md#globally

#Tutorial
http://ucf.github.io/fuelphp-crash-course/
> When using MAMP to connect mysql, remember to set port 8889.

#Elastica
install using composer
add ```"ruflin/Elastica": "dev-master"``` to composer.json in fuelphp.
then run ``` php composer.phar update```

#elasticsearch
"elasticsearch/elasticsearch": "~2.0"

#more
http://elastica.io

[FuelPHPでAJAX](http://atmarkplant-dj.blogspot.jp/2012/10/fuel-php-ajax.html)
master.jsonならpost_masterで受け取る
これはcontroller_restを拡張したクラスです。

#config file
[独自の設定ファイル](http://ackintosh.github.io/blog/2013/04/29/custom-configuration-file-for-fuelphp/)
config фолдер дотор profile.php үүсгэсэн бол, доорх аргаар ашиглаж болно. Харин доторх нь return хэлбэртэй байх хэрэгтэй.
Жишээ нь: 
```
<?php 
	return array(
    	'name' => 'akihito',
    	'twitter' => 'NAKANO_Akihito',
    );
?>
```

Config::load('profile', true);
echo Config::get('profile.name');// akihito

#for each
foreach ($array as $x)
foreach ($array as $key => $value)

#debugging
$this->response("Hello");??

perl a.pl 1>out 2>err
python a.py 1>out 2>err
гэх мэтээр ашиглаж болно.


#Creating ZIP file

```php
$headers = array(array('col1', 'col2', 'col3'), array('col1','col2'));
$csv = array(array(), array());
foreach ($rows as $row)
	$csv[0][] = array($row['id'], $row['name'], $row['city']);
foreach ($nodes as $node)
	$csv[1][] = array($node['id'], $node['title']);

	$zipName = tempnam("tmp", "zip");
	$zip = new ZipArchive();
	$result = $zip->open($zipName, ZipArchive::CREATE | ZipArchive::OVERWRITE);
	for ($i=0; $i<2; $i++){
		// create a temporary file
		$fd = fopen('php://temp/maxmemory:1048576', 'w');
		if (false === $fd) {
			die('Failed to create temporary file');
		}
		// write the data to csv
		fputcsv($fd, $headers[$i]);
		foreach($csv[$i] as $line) {
			fputcsv($fd, $line);
		}
		// return to the start of the stream
		rewind($fd);
		// add the in-memory file to the archive, giving a name
		$zip->addFromString('table'.($i+1).'.csv', stream_get_contents($fd) ) or die ("ERROR: Could not add file:".$i);
		fclose($fd);
	}
	$zip->close();

	if (file_exists($zipName)) {
		header("Pragma: public");
		header("Expires: 0");
		header("Cache-Control: must-revalidate, post-check=0, pre-check=0");
		header("Cache-Control: public");
		header("Content-Description: File Transfer");
		header("Content-type: application/octet-stream");
		header("Content-Disposition: attachment; filename=data.zip");
		header("Content-Transfer-Encoding: binary");
		header("Content-Length: ".filesize($zipName));
		ob_end_flush();
		@readfile($zipName);
		exit;
	}
```

#returning zip
http://stackoverflow.com/questions/12411481/php-download-script-creates-unreadable-zip-file-on-mac
#multiple csv
http://stackoverflow.com/questions/27707620/php-create-multiple-csv-files-in-memory-then-compress

#views
http://fuelphp.com/docs/general/views.html

Pure PHP
----------

#Big O for PHP functions
http://stackoverflow.com/questions/2473989/list-of-big-o-for-php-functions

#date
date_default_timezone_set('Asia/Tokyo');
date("Y-m-d H:i:s");

#split
explode(" ",$str)

#Sort array by field
http://stackoverflow.com/questions/10000005/php-sort-array-by-field
function cmp($a, $b)
{
    return strcmp($a["title"], $b["title"]);
}

usort($array, "cmp");

#sort associative array by value
```php
arsort($array);
```
