Headings
Setext-Style:

Header 1
======= 

Header 2 
----------

atx-Style (Closing #’s are optional):
# Header 1 #
## Header 2 ##
### Header 3 ### 
#### Header 4 
##### Header 5 
###### Header 6

Phrase Emphasis
*italic* or _italic_ **bold** or __bold__

Horizontal Rules
Three or more dashes or asterisks.
--- or * * * or - - - - Manual Line Breaks
End a line with two or more spaces:
Roses are red, Violets are blue.

Images
Inline (titles are optional):
![alt text](/path/img.jpg)
![alt text](/path/img.jpg “Title”)
Reference-style:
![alt text][id]
[id]: /path/to/img.jpg “Title” [1]: /path/myimage.jpg “My Image”
Blockquotes
E-mail-style angle brackets are used for blockquotes and can be nested.
> An example, single level. >> A nested blockquote.
> ### Headers in blockquotes >
> * You can quote a list.
> * Etc.
Code Spans
<code> spans are delimited by backticks:
You can include literal backticks like ```this```.
Automatic Links
For creating automatic links for URLs and e-mail addresses:
<http://www.example.com> will turn into:
<a href=”http://www.example.com”>http://www. example.com</a>
Email addresses will be HEX encoded

Preformatted Code Blocks
Indent every line of a code block by at least 4 spaces or 1 tab, and use a colon at the end of the preceding paragraph:

This is a normal paragraph:
	This is a preformatted code block.

Preceded by a space, the colon disappears :
	
	This is a preformatted code block.

Lists
Ordered, without Paragraphs (note that the order of the numbers is not important as the output will be in stan- dard <ol><li>item 1</li><li>item 2</li></ol> format): 

1. Foo
2. Bar

Unordered, with Paragraphs (optionally can use dashes, plus signs or asterisks):
* A list item.
With multiple paragraphs. 
* Bar
Nested Lists

* Millimeters
	* Centimeters
* Pixels 
	1. Ems
	2. Points 
		* Picas
	3. Inches
* Kilometers

Links
Inline links:
An [example](http://url.com/ “title”)
Reference-style links (titles are optional):
An [example][id]. Then, anywhere else in the document, define the link:
[id]: http://wwww.daringfireball.com/ “Title”
Backslash Escape Characters
Markdown provides backslash escapes for the following:
\ backslash
` backtick
* asterisk
_ underscore
{} curly braces
[] square brackets
() paranthases
# hash mark
+ plus sign
- minus sign (hyphen)
. dot
! exclamation mark
For example,
\* these would be listeral asterisks\*