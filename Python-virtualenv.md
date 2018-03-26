#
#Install from system python
virtualenv --python=/usr/bin/python2.6 <path/to/new/virtualenv/>


#Pyenv
https://github.com/pyenv/pyenv/blob/master/COMMANDS.md

#Error clang in pyenv 2.7.6 when installing sth
OK for python >=2.7.8 

#ssl issue 
CFLAGS="-I$(brew --prefix openssl)/include" \
LDFLAGS="-L$(brew --prefix openssl)/lib" \
pyenv install -v 3.4.3