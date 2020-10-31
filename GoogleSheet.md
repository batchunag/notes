#String Regex
`A1&"*"`

#Vlookup with regex

`
=VLOOKUP(A2&"*",$G$1:$I$99, 3, FALSE)
`
3 means column I,
FALSE: column value is not sorted.


