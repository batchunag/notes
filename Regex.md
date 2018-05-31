#test online
https://regex101.com/

#Non-greedy
(.+$) end of line

a? a is optional
() non capturing group
(?:) non capturing group
#route(?:\?cb=(.+$))?
> matches
	routea
	route?=aa
	route?cb=
>non-matches
	route
	route?cb=http:aa
	route?cb=aa




