# If i want to count the words in the files, and the files are listed in different subdirectory, and i know the name of these files， how to achieve that

## find . -name '*.txt' -exec wc -w {} +
This will find all txt file (-name '*.txt'） in the current working directory (.) and recursing into subdirectories and for each result will execute (-exec [...] \;) wc -w passing that filename ({}) as an argument

## find . \( -name '*.txt' -o -name '*.csv' \) -exec wc -w {} +
If you want to find multiple type of files, like txt file and csv file


# Write a shell script to word counts on individual files

#!/bin/bash
for file in *;
do 
if [[ -s $file ]];
then wc -w $file >> wc.txt;
else 
echo "${file} sorry this file is empty" >> wc.txt; 
fi;
done
