#Pathogen
https://github.com/tpope/vim-pathogen
Plugin г.м суулгахад амар.
```
mkdir -p ~/.vim/autoload ~/.vim/bundle && \
curl -LSso ~/.vim/autoload/pathogen.vim https://tpo.pe/pathogen.vim
```
Дараа нь доорх коммандыг ~/.vimrc файл дотроо оруулна. (Хамгийн эхэнд?)
`execute pathogen#infect()`

#NerdTree
https://github.com/scrooloose/nerdtree
Pathogen ашиглаад суулгая гэвэл энэ кодыг уншуулахад болно.
```
cd ~/.vim/bundle
git clone https://github.com/scrooloose/nerdtree.git
```

Нэмэлт:
^w hkjl товчнуудаар 4 зүгийн цонхнуудруу шилжих боломжтой.

#Code Folding
http://stackoverflow.com/questions/2362914/fold-function-in-vim

Vim folding commands
---------------------------------
> 
zf#j creates a fold from the cursor down # lines.
zf/ string creates a fold from the cursor to string .
zj moves the cursor to the next fold.
zk moves the cursor to the previous fold.
za toggle a fold at the cursor.
zo opens a fold at the cursor.Ø
zO opens all folds at the cursor.
zc closes a fold under cursor. 
zm increases the foldlevel by one.
zM closes all open folds.
zr decreases the foldlevel by one.
zR decreases the foldlevel to zero -- all folds will be open.
zd deletes the fold at the cursor.
zE deletes all folds.
[z move to start of open fold.
]z move to end of open fold

Autocompletion
----
YouCompleteMe
downloaded to bundle folder but couldn't install

#Help FILE
https://www.cs.swarthmore.edu/help/vim/reformatting.html

14== auto indent

#Find and replace
:[range]s/foo/bar/g
:33,35s/^..//g => removes first 2 character of line from 33 to 35
:%s/foo/bar/g => throughout the file
:.,+3s/foo/bar/g => 3lines from current line
^ : line start

#Number of pattern matches
:%s/pattern//gn


