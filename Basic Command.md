### Word Count files in different subdirectory

1. find . -name '*.txt' -exec wc -w {} +

This will find all txt file (-name '.txt'） in the current working directory (.) and recursing into subdirectories and for each result will execute (-exec [...] \;) wc -w passing that filename ({}) as an argument

2. find . \( -name '*.txt' -o -name '*.csv' \) -exec wc -w {} +

If you want to find multiple type of files, like txt file and csv file


### Write a shell script to word counts on individual files

#!/bin/bash
for file in *;
do 
if [[ -s $file ]];
then wc -w $file >> wc.txt;
else 
echo "${file} sorry this file is empty" >> wc.txt; 
fi;
done


## wget fasta file
wget "http://eutils.ncbi.nlm.nih.gov/entrez/eutils/efetch.fcgi?db=nucleotide&id=CP002565.1&rettype=fasta" -O b.fa

## add a character into a string
for i in *.gz; do mv $i `echo $i | sed -r -e 's/_/_S/'`; done;
for i in *.gz; do mv $i `echo $i | sed -r -e 's/^([^_]*)_(.*)/\1_S\2/'`; done;
