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

#strftime for datetime variable
my $start = DateTime->new(day=>1, month=>6, year=>2016);
$start->strftime("%Y_%m_%d");

#copy array
my @ar1 = (10,10,10);
@a=[@ar1];

#database
my $data = $db->execute_decoded($sql);
-->> $data is number of rows
foreach my $d (@{$data}) {
 print $d->[0];
}

#readfile
my $file = "today.txt";
open(my $fh, '<:encoding(UTF-8)', $file)
	or die "Could not open file '$file' $!";
my $row = <$fh>;
chomp $row;

#Download module
cpan File::Slurp

#Ignore confirmations
perl -MCPAN -e 'my $c = "CPAN::HandleConfig"; $c->load(doit => 1, autoconfig => 1); $c->edit(prerequisites_policy => "follow"); $c->edit(build_requires_install_policy => "yes"); $c->commit'

#CPAN mirror
ftp://ftp.kddilabs.jp/CPAN/
