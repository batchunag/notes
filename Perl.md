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

Time now
my $dt = DateTime->now(time_zone=>'local');
$dt->subtract(days => 14);

#copy array
my @ar1 = (10,10,10);
@a=[@ar1];

#database
my $data = $db->execute_decoded($sql);
-->> $data is number of rows
foreach my $d (@{$data}) {
 print $d->[0];
}


