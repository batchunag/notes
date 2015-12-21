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
% defualt words change
\renewcommand{\figurename}{Зураг}
\renewcommand{\tablename}{Хүснэгт}
\renewcommand\lstlistingname{Код}
\renewcommand\chaptername{Бүлэг}
```

Making glossary