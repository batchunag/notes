#Print to HTML
https://github.com/joelpt/sublimetext-print-to-html

Sublime packages

>OmniMarkupPreviewer: Live preview  
	Command + Alt + O  
>Seti UI : (Sublime 3) UI


Japanese 入力 (use tab for list)
-----
Comment out auto_completion using which recognizes "tab" button

> 
Packages/Default folderを作り、Default\ \(OSX\).sublime-keymap 設定ファイルを置く。 その後、Key Bindings - Defaultから設定を開くとちゃんと編集できる。

```
$ cd Library/Application\ Support/Sublime\ Text\ 3
$ mkdir Packages/Default
$ mv ~/Default\ \(OSX\).sublime-keymap ./Packages/Default/
```
> ３行目はなかったら、Defaultの方からinsert_best_completion, replace_completion_with_next_completion : tab -> shift + tab

#Latex Compiler & pdf sync
http://economistry.com/2013/01/installing-and-using-latex-for-mac/
LatexTools + Skim
Default viewer settings: 
Library/Application\ Support/Sublime\ Text\ 3/Packages/LaTeXTools/jumpToPDF.py

#Latex autocomplete
Packages: LaTexIng, Latex-cwl

#Find and replace regex
```regex
(\n[' ']*)(natwidth=[0-9]+)
$1 $2 or $& for all
```

#Syntax highlighting: Markdown Extended, Monokai Extended

Make sure that the syntax for the current file is set to Markdown Extended:



#update on ubuntu 16.04 & higher
http://tipsonubuntu.com/2017/05/30/install-sublime-text-3-ubuntu-16-04-official-way/

#Print code to browser
Print to HTML--> Not showing to browser on Ubuntu 18.04.
ExportHtml--> Use right click on mouse. Can be customized with hot key.