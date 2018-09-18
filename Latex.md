Fancy Chapter Headings
----
http://tex.stackexchange.com/questions/23477/fancy-chapter-headings

Watermark
---
> Normal
	```latex
	\usepackage{draftwatermark}
	\SetWatermarkText{Confidential}
	\SetWatermarkScale{5}
	\SetWatermarkColor[rgb]{0.7,0,0}
	```
> On top layer 
	```
	\usepackage[printwatermark]{xwatermark}
	\newwatermark*[allpages,color=red!50,angle=45,scale=5,xpos=0,ypos=0]{ANTS баг}
	```

Multilanguage
----
http://tex.stackexchange.com/questions/83293/package-clash-in-multilingual-report


tcolorbox
----
http://mirror.unl.edu/ctan/macros/latex/contrib/tcolorbox/tcolorbox.pdf

code inside tcb listing

```latex
\newtcblisting{ccode}{left=6mm, colframe=black!50!white,listing only,listing options={style=tcblatex,language=C}}
```

Math
----
Multi-valued function

```latex
\begin{equation}
dp[i+1][j+1]=
\left\{
	\begin{array}{ll}
		 \max(dp[i][j]+1, dp[i][j+1], dp[i+1][j]) \mbox{ хэрэв } s_{i+1}=t_{j+1}\\
		 \max(dp[i][j+1], dp[i+1][j] \mbox{ бусад тохиолдолд }
	\end{array}
\right.
\end{equation}

```

Geometry
---
ftp://xyz.lcs.mit.edu/pub/CTAN/macros/latex/contrib/geometry/geometry.pdf

\usepackage[top=20mm, bottom=2mm, left=20mm, right=20mm,
includehead, includefoot]{geometry}


#Бүлгийн нэр header-т хэвлэх
```latex
\pagestyle{fancy}
\fancyhf{}
\fancyhead[LE]{\leftmark}
\fancyhead[RO]{\rightmark}
```

Хэсгийн нэрийг нэг шугаманд оруулах
Коммент ногоон өнгөтэй болгох
#Footnote хийх
\footnote{Монголын хувьд ...}

#Програмын Listing алга болгох -> Эх код болгож солих
#OK Table -> Хүснэгт
```latex
% default words change
\renewcommand{\figurename}{Зураг}
\renewcommand{\tablename}{Хүснэгт}
\renewcommand\lstlistingname{Код}
\renewcommand\chaptername{Бүлэг}
```

#Making index
\usepackage{imakeidx}
\makeindex

\addcontentsline{toc}{chapter}{Индекс}
\printindex

*Multiindex* 
\makeindex[name=person,title={Index of persons}]

#xindy
> 
```
\providecommand*\lettergroup[1]{} % Put before imakeidx to remove lettergroups
\usepackage[xindy]{imakeidx}
\usepackage{idxlayout} %[initsep=0mm]
\makeindex[name=eng,title={English Index}]
\makeindex[name=mon,title={Товьёг}]

%resolve inputenc cyrillics
\makeatletter 
\newcommand{\rindex}[2][\imki@jobname]{%
  \index[#1]{\detokenize{#2}}%
}
\makeatother
```

> texindy to generate ind file
`texindy -v -L mongolian -C utf8 mon.idx`



#lsblisting utf8 encoding
add texcl=true to the \lstset
https://tex.stackexchange.com/questions/89638/how-to-set-utf8-in-a-lstlisting-error-received

#Glossary and acronyms
https://texblog.org/2014/01/15/glossary-and-list-of-acronyms-with-latex/


#Beamer Template | Slide
http://xaro.hatenablog.jp/entry/2013/09/18/020615
http://www.opt.mist.i.u-tokyo.ac.jp/~tasuku/beamer.html

#Equation aligned left
\usepackage[fleqn]{amsmath}
\begin{flalign}
& a:=b
\end{flalign}

#Space in math
{~~~}

#Column width can be set in tabularx
\usepackage{tabularx, booktabs}
\newcolumntype{Y}{>{\centering\arraybackslash}X}
\begin{tabularx}{0.75\textwidth}{c *{6}{Y}}
\toprule
Foo bar
 & \multicolumn{3}{c}{Fantastical aardvarks}  
 & \multicolumn{3}{c}{Spelunking elephants}\\
\cmidrule(lr){2-4} \cmidrule(l){5-7}
  & A & B & C & A & B & C\\
\midrule
 5  & 87 &  5 &  2 & 82 & 18 & 48\\
 6  &  5 & 43 &  4 &  7 & 47 &  4\\
 7  &  7 & 18 & 63 &  2 &  9 & 99\\
\bottomrule
\end{tabularx}

#Circling for list enumeration
\newcommand*\circled[1]{\kern-2em%
  \put(0,4){\color{white}\circle*{18}}\put(0,4){\circle{16}}%
  \put(-3,0){\color{black}\bfseries\large#1}~~}


#Cite tag in other page
\ref{fig22:bintree}
\label{ig22:bintree}

#Box for inline side notes
\newtcolorbox{sidebox}[1][]
{
 arc=3mm,
 left skip=42mm,
 beforeafter skip=0cm,
 colframe=white!0!white,
}

#Nice symbols dingbat
\usepackage{dingbat}
\leftpointright
>  you may need \usepackage{pifont}


#Aligned formula in bold
\vspace*{-3mm}
{\mathversion{bold}
\begin{equation*}
\begin{aligned}
dp[i][j] = \sum_{k=0}^j dp[i-1][j-k]
\end{aligned}
\end{equation*}
}

\vspace*{-3mm} 
\noindent 

#titlespacing default value
\titlespacing*{\section}
{0pt}{*1}{*1}
--> times 1