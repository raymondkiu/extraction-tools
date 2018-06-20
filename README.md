# informatics-tools
Some small and simple scripts useful for various bioinformatics purposes. 

### extract-contigs.pl
This convenient Perl script is able to extract contigs of FASTA files either by contig name or a list of contig names.
```
$ extract-contigs.pl single CONTIGNAME FASTAFILE
```
or with a list of contigs
```
$ extract-contigs.pl list LISTNAME FASTAFILE
```
To save into a new file, use ">" sign
```
$ extract-contigs.pl list LISTNAME FASTAFILE > NEW_FILENAME
```
### ver-horizontal.sh
This Bash script converts a list to horizontal view on the standard output for various automation purposes.
```
$ ver-horizontal.sh LIST
```
For instance, a file named LIST
```
hello
world
happy
```
will be converted to 
```
hello world happy
```
### assembly-stats.pl
This Perl script gives you general assembly statistics including contig number, genome size, largest contig (bases), GC content, N count and gap count. It takes the inputs of FASTA assemblies.
```
$ assembly-stats.pl FASTAFILE
```
It generates data on standard output as follows:
```
Sample_ID  Genome  Contigs Mean    Median  N50     Largest GC(%)   N_count N(%)    Gap_count
test.fasta 158     2       79      89      89      89      5.95    26      16.46   4
```
#### Output explanations
Genome: Genome size
Contigs: Number of contigs in the fasta file
Mean: Average size of contigs in bases
Median: Size of median contig
N50: Yardstick of assembly quality - 50% of the contigs are larger than this size (in nucleotide bases) 
Largest: Size (nucleotide bases) of largest contigs
GC(%): GC (guanine and cytosine) content of the genome
N_count: Number of N found in the genome (uncertain base calling)
N(%): N count in percentage
Gap_count: count "-" in the fasta file, usually appears in alignment file

### reverse-complement.sh
This Bash script generates reverse complement for nucleotide FASTA files. That is, A -> T, G -> C and vice versa.
```
$ reverse-complement.sh -o OUTPUT_FILENAME FASTAFILE
```
Option -o can be omitted, the default output filename is FASTAFILE-complement.fasta
