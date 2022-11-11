# Researching Commands (FIND)

## -type

```
krutidharanipathi@Krutis-MBP docsearch % cd technical 
krutidharanipathi@Krutis-MBP technical % touch new_1.txt  
krutidharanipathi@Krutis-MBP technical % find . -type f -mmin -2
./new_1.txt
```
I first created a text file called new_1.txt in technical. I then used find . -type f -mmin -2 to check what files where created in the last 2 minutes and " ./new_1.txt " was the output.

```
krutidharanipathi@Krutis-MBP technical % find .  -type f -amin -10
./new_1.txt
krutidharanipathi@Krutis-MBP technical % find .  -type f -amin -10
./new_1.txt
./911report/chapter-2.txt
```
I wanted to try another one with time specfically access time to see what happens. To do this I first checked what the output was before I changes a file and the only output I got was the file I recently created. I then changed " ./911report/chapter-2.txt " by adding a random space. I then ran amin again and got an output of both " ./new_1.txt " and " ./911report/chapter-2.txt ". 

```
krutidharanipathi@Krutis-MacBook-Pro technical % find . -type d
.
./government
./government/About_LSC
./government/Env_Prot_Agen
./government/Alcohol_Problems
./government/Gen_Account_Office
./government/Post_Rate_Comm
./government/Media
./plos
./biomed
./911report
```

I wanted to find all the files in the current directory that I am in. The directory that I am in is techincal so I would find all the files in technical. I used "find . -type d" to do this. The output I got is printed above.


## -size

```
krutidharanipathi@Krutis-MBP technical % find . -size +200k
./government/About_LSC/commission_report.txt
./government/Env_Prot_Agen/bill.txt
./government/Gen_Account_Office/GovernmentAuditingStandards_yb2002ed.txt
./government/Gen_Account_Office/Statements_Feb28-1997_volume.txt
./government/Gen_Account_Office/d01591sp.txt
./911report/chapter-13.4.txt
./911report/chapter-13.5.txt
./911report/chapter-3.txt
```

One command that I tried with find is size. I wanted to find the files that are greater than 200 kilobytes in size and I searched for those. the +200k is the more then 200 kilobytes that we are searching for. This is the output that I got. 

```
krutidharanipathi@Krutis-MacBook-Pro technical % find . -size -1k
.
./government
./government/About_LSC
./government/Env_Prot_Agen
./government/Alcohol_Problems
./government/Post_Rate_Comm
./plos/pmed.0020191.txt
./plos/pmed.0020226.txt
./new_1.txt
./911report
```

I can also search for files that are less than a size instead of only a size greater like I did above. I used the -1k to find all the files that are less than 1 kilobyte in size. I then got an output with a list of files that are less than that size. 

```
krutidharanipathi@Krutis-MacBook-Pro technical % find . -type f -exec ls -s {} + | sort -n -r | head -3
600 ./government/Gen_Account_Office/Statements_Feb28-1997_volume.txt
592 ./government/Gen_Account_Office/d01591sp.txt
576 ./911report/chapter-13.5.txt
```
I then used the -size command-line option to find the 3 largest files in the directory that I am currently in. It then gives the output of these 3 files recursively so I can see what the 3 largest files in the directory are. This is the output that I got.

## -name

```
krutidharanipathi@Krutis-MacBook-Pro docsearch % find ./technical -name chapter-1.txt 
./technical/911report/chapter-1.txt
```
I was in the doc search directory and I wanted to find where where chapter-1.txt would be. By using "find ./technical -name chapter-1.txt " I was able to locate the file.


```
krutidharanipathi@Krutis-MacBook-Pro docsearch % find ./ -type f -name "*.txt" -exec grep 'synergistically'  {} \;
        mastery of facts, and we enter an era of medical practice that will develop synergistically
        across species [17,20,21] and stimulated synergistically by both IL-6 and IL-1β [22–25].
        differentiation and between GA and ABA in germination. Other processes are synergistically
        ERF1 expression, and treatment with both hormones synergistically
        with MEF2 to synergistically activate selective ST muscle genes and also serves as a target
          lipopolysaccharide (LPS)) that acts synergistically with
        synergistically increases PH-20-mediated inhibition of
        and WOX1 mediate apoptosis synergistically. Overexpressed
        Progesterone interacts synergistically with estrogen in
        synergistically, suggesting Gleevec can potentiate the
          Gleevec and cisplatin synergistically inhibited the
          synergistically with cisplatin. Cisplatin causes two
          with NF-κB, resulting in a complex that synergistically
          synergistically to transactivate the reporter construct
        these two ligands affect virus infectivity synergistically
          1and 2, Fig. 3). CAP and sCD4 synergistically inhibited
        sites on HIV-1 and acting synergistically.
          but interacted synergistically with it [ 12 ] . These
        synergistically or cooperatively. The latter may either
          1 is synergistically influenced by α 
          synergistically with a primary defect (either nuclear or
        Stat3 can act synergistically with other coactivators to
        synergistically with other c oactivators to stimulate SHRs
```

I wanted to find all the txt files that contained the word "synergistically". I printed out all the lines from these files that contian the word. I combined grep and find to find it and also used type along with name to find these files. I used the command " find ./ -type f -name "*.txt" -exec grep 'synergistically'  {} \;" I found all of these lines and they were shown as an output. 

```
krutidharanipathi@Krutis-MacBook-Pro docsearch % cd technical                                                     
krutidharanipathi@Krutis-MacBook-Pro technical % cd government                                                                 
krutidharanipathi@Krutis-MacBook-Pro government % find ./Alcohol_Problems -name Session2-PDF.txt -exec rm -i {} \;
remove ./Alcohol_Problems/Session2-PDF.txt? y
```
I wanted to remove the file Session2-PDF.txt so I used the command above to do so. I first cd into the correct directory with was government. From there I used "find ./Alcohol_Problems -name Session2-PDF.txt -exec rm -i {} \;" to remove the file. It then asked me if I was sure I wanted to remove it and I typed y which removed the file from the directory