# Useful Commands
***

## Sequence lengths in a Fasta file

Reference: https://stackoverflow.com/questions/23992646/sequence-length-of-fasta-file

    awk '/^>/ {if (seqlen){print seqlen}; print ;seqlen=0;next; } { seqlen += length($0)}END{print seqlen}' file.fa

## Counting Fasta files in a directory

    ls -lR /path/to/dir/*.fasta | wc -l

## Counting Sequences in a Fasta file

    grep -c "^>" *.fas

## Remove files based on names in a file

    rm -r `cat file.txt`

## Compressing and extracting folders (or files)

To create and archive...

    tar -czvf name-of-archive.tar.gz /path/to/directory-or-file

To compress multiple items into one archive file, list additional items at the end.

To extract...

    tar -xzvf archive.tar.gz

## Remove or move files listed in a text file

rm -r `cat list_to_remove.txt`

rsync -a /source/directory --files-from=/full/path/to/listfile /destination/directory
