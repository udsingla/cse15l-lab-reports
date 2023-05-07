# Lab Report 3 - Researching Commands

I have chosen the command `grep` and researched command-line options for it.

Following are the command-line options that I found and decided to include in the lab report:
* `-i` - The "-i" option in the grep command stands for "ignore case." When you use "-i" with grep, it makes the search case-insensitive, which means that the pattern or string you are searching for will match regardless of whether it is in upper case or lower case.

It is useful when we want to find lines with a particular word which can have some characters capitalized depending if it is the first word in the line or in between.

Example 1:
```
$ grep 'Rna' technical/biomed/1471-2180-1-28.txt
          GTP; 0.5 mM cap analog (NEBL); 10 mM DTT; 40 U of Rnasin
          
$ grep -i 'Rna' technical/biomed/1471-2180-1-28.txt
        alternatives to HIV could be considered as potential "live"
        poxviruses (vaccinia and canarypox), small RNA viruses
        replicates entirely in the cytoplasm through RNA directed
        RNA polymerization and is incapable of integrating into the
        NS4A, NS4B and NS5 include an RNA-directed RNA polymerase
          RNAase-free water in preparation for transcription. The
          GTP; 0.5 mM cap analog (NEBL); 10 mM DTT; 40 U of Rnasin
          (Promega); 30 U of SP6 RNA polymerase; and 1 × SP6 RNA
          full length viral RNA, were used to transfect
```
As you can see in the above examples, when we search for `'Rna'` without `-i`, it returns just 1 line. However, when we run the line with `-i` as a command-line option for `grep`, it returns lines which contain substring 'rna' irrespectinve of the case. 

Example 2:
```
$ grep -i 'Ax' technical/government/Alcohol_Problems/*
technical/government/Alcohol_Problems/Session2-PDF.txt:maximize screening test performance.40
technical/government/Alcohol_Problems/Session3-PDF.txt:alcohol-related trauma. Br J Oral Maxillofac Surg
```
In the above example, we search all the files in the 'Alcohol_Problems' directory recursively for the string `'Ax'` which has a capital 'A', but in the output we see both lines which contain a lowercase 'a' and 'x'. This shows that `-i` allows us to search files for a string while ignoring the case and only focusing on the position of the characters.

***

* `-l` - The "-l" option in the grep command stands for "files with matches." When you use "-l" with grep, it prints only the names of the files that contain at least one matching line or pattern, rather than printing the actual matching lines.

This is useful when you want to quickly find out which files in a directory or a set of files contain a specific pattern, without having to manually search through each file.

Example 1:
```
$ grep -l 'Rna' technical/biomed/*
technical/biomed/1471-2164-2-6.txt
technical/biomed/1471-2180-1-28.txt
technical/biomed/1471-2202-3-3.txt
technical/biomed/1471-2350-3-12.txt
technical/biomed/1476-4598-1-6.txt
technical/biomed/1477-7827-1-23.txt
technical/biomed/bcr303.txt
```
In this above example we search every file in directory biomed to look for string 'Rna' and the `-l` option provides the paths/names of the files which cointain that substring in them.

Example 2:
```
$ grep -l 'RNA' technical/biomed/ar104.txt
technical/biomed/ar104.txt



$ grep -l 'Rna' technical/biomed/ar104.txt

```
When we search in only one file, it returns the path of that file if that file contains that string. Otherwise it outputs nothing as shown above in the example.

***

* `-c` - The "-c" option in the grep command stands for "count." When you use "-c" with grep, it prints only the count of the number of lines that match the pattern, rather than printing the actual matching lines.

This is useful when you want to quickly find out how many lines in a file or a set of files contain a specific pattern, without having to manually count the number of lines.

Example 1:
```
$ grep -c 'RNA' technical/biomed/ar104.txt
3
```
The above example tells us that there are 3 lines in the file 'ar104.txt' which contain the substring 'RNA'. This helps us by telling us the number directly instead of displaying the lines containing that substring.

Example 2:
```
$ grep -c 'rna' technical/government/Alcohol_Problems/*
technical/government/Alcohol_Problems/DraftRecom-PDF.txt:3
technical/government/Alcohol_Problems/Session2-PDF.txt:4
technical/government/Alcohol_Problems/Session3-PDF.txt:2
technical/government/Alcohol_Problems/Session4-PDF.txt:21
```
When searching through all the files in a directory, it lists the path of every file along with outputting the number of times the substring appears in each of the files. This is shown in the example above.

***

* `-v` - The "-v" option in the grep command stands for "invert match." When you use "-v" with grep, it prints only the lines that do not match the specified pattern, rather than printing the lines that do match.

This is useful when you want to filter out lines with a certain string. 

Example 1:
```
$ grep -v 'a' technical/biomed/cc350.txt




        Introduction
        skin blood flow [ 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17,


        U-test.


        Results
        insertion.
        the 24 h study period (norepinephrine, 0.08-0.78 μg/kg per
        insertion (
        respectively).
        P = 0.8).
      

        Discussion
        differences in blood flow of up to sixfold [ 17]. The
        this study, these were not influenced by insertion of the




```
As we see in the above example, the `-v` option returns all lines which do not contain the string 'a' in them. It allows us to exclude certain lines or patterns from the output. 

Example 2:
```
$ grep -v 'a' technical/government/Alcohol_Problems/*
technical/government/Alcohol_Problems/DraftRecom-PDF.txt:
technical/government/Alcohol_Problems/DraftRecom-PDF.txt:
technical/government/Alcohol_Problems/DraftRecom-PDF.txt:
technical/government/Alcohol_Problems/DraftRecom-PDF.txt:
technical/government/Alcohol_Problems/DraftRecom-PDF.txt:Discussion of
technical/government/Alcohol_Problems/DraftRecom-PDF.txt:
technical/government/Alcohol_Problems/DraftRecom-PDF.txt:steering committee to consider. During the conference, the steering
technical/government/Alcohol_Problems/DraftRecom-PDF.txt:discussion.
technical/government/Alcohol_Problems/DraftRecom-PDF.txt:them.
technical/government/Alcohol_Problems/DraftRecom-PDF.txt:consequences.
technical/government/Alcohol_Problems/DraftRecom-PDF.txt:The problem is the consequences resulting from excessive
technical/government/Alcohol_Problems/DraftRecom-PDF.txt:drinking.
technical/government/Alcohol_Problems/Session2-PDF.txt:
technical/government/Alcohol_Problems/Session2-PDF.txt:
technical/government/Alcohol_Problems/Session2-PDF.txt:
technical/government/Alcohol_Problems/Session2-PDF.txt:
technical/government/Alcohol_Problems/Session2-PDF.txt:Session 2.
technical/government/Alcohol_Problems/Session2-PDF.txt:
technical/government/Alcohol_Problems/Session2-PDF.txt:Alcohol problems defined
technical/government/Alcohol_Problems/Session2-PDF.txt:tests
technical/government/Alcohol_Problems/Session2-PDF.txt:drinks).
...
More Outputs but didn't include them due to lack space
```
In this example we search through every file in Alcohol_Problems directory. The command line option outputs every line which does not have the string 'a', along with the file path with every line.

***

These were some of the command-line options for `grep`. These are very helpful in refining and making our searches more efficient and accurate. We can also use these options together for even more complex search operations.

The sources from where I found out about these command line options were:
* https://man7.org/linux/man-pages/man1/grep.1.html
* ChatGPT (looked up examples of implementation)
