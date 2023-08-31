# Download GenBank genomes by taxon id

This script downloads all genome assemblies
from the NCBI FTP server that belong to the taxonomy sub-tree denoted
by the taxon id given as argument.

For example:
```
./download-genbank-genomes.pl 5052
```
will download all Aspergillus genome assemblies.

The file type can be set using command line option -t using one of the values
`fna`, `faa`, or `gbff` (default),  for example:
```
./download-genbank-genomes.pl -t fna 5052
```

By default, only genomes with assembly_level "Complete Genome" or "Chromosome" are downloaded.
Setting option -a will download all genomes regardless of assembly level:

```
./download-genbank-genomes.pl -a -t fna 5052
```

Additionally, genomes can be filtered by the RefSeq category "representative genome" or "reference genome" using option `-r`.

When setting option `-g`, only assemblies with no matching assembly in RefSeq will be downloaded.

When setting option `-e`, assemblies that were excluded from RefSeq are not downloaded.

Files are downloaded with `wget`.

Copyright 2021 Peter Menzel <pmenzel@gmail.com>

