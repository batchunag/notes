#comment
=pod
=cut

#break in a loop
last;

#continue
next;

#iterate with index
for my $i (0 .. $#x) {
    print "$i: $x[$i]\n";
}

#size of array
`scalar(@a)`
`$#a` ->index of last element

#datetime

```perl
my ($day, $month, $year) = (localtime)[3,4,5];
$year+=1900;
$month+=1;
```