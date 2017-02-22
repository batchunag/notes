yums
===
yum list available | grep igraph


#Install R and Rmecab
http://senyoltw.hatenablog.jp/entry/2015/06/26/052629



#installing mecab for python from source
http://progmemo114.hatenablog.com/entry/2016/07/02/145015
1) download groonga
2) install mecab
3) pip install mecab-python3

> Basic packages
	sudo yum groupinstall 'Development Tools'
	yum install glibc-static

> /usr/bin/ld: cannot find lm, ld errors:
	yum install gcc gcc-c++ make openssl-devel
> MeCab_wrap.cxx:149:20: fatal error: Python.h: No such file or directory #include <Python.h>の場合:
	sudo yum -y install python-devel
> /usr/bin/ld: cannot find lz errors:
	yum install zlib zlib-devel zlib-static

igraph, numpy can be installed by yum