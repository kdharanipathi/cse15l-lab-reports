# Researching Commands

## Find

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

Another command that I tried with find is size. I wanted to find the files that are greater than 200 kilobytes in size and I searched for those. the +200k is the more then 200 kilobytes that we are searching for. This is the output that I got. 

## Grep

```
krutidharanipathi@Krutis-MBP biomed % grep -win "general" 1468-6708-3-7.txt
15:        alpha-1 antagonists in general or doxazosin in particular
268:        peripheral alpha-1 antagonists in general and doxazosin in 
```
For the grep command I looked in a specfic file to find lines that contain the word "general". The output to this command was the line with the word "general" and the line number. 

```
krutidharanipathi@Krutis-MBP biomed % grep -win -B 2 "general" 1468-6708-3-7.txt
13-        [ 1 ] . Prior to this publication, there had been no
14-        obvious suggestion of a mechanism by which peripheral
15:        alpha-1 antagonists in general or doxazosin in particular
--
266-        enough to double the average incidence of CHF.
267-        The literature suggests several mechanisms by which
268:        peripheral alpha-1 antagonists in general and doxazosin in
```
I then did a similar command where I again looked for the word general in a certain file but I also had it print out the output for 2 lines before the word "general" everytime general shows up in the line. 

```
krutidharanipathi@Krutis-MBP technical % grep -wirl "descriptively" . 
./biomed/1472-6947-2-4.txt
./biomed/1468-6708-3-7.txt
```

The last thing that I did with grep is look for the word "descriptively" in all the files in technical and it gave the output of whatever files have the word "descriptively" in it.


## Less

```
krutidharanipathi@Krutis-MBP biomed % less 1471-2164-3-13.txt 1471-2164-3-15.txt
```

Using this less command I found these 2 files and showed the output of everything that is in these two files and was able to navigate between these to files. 

```
n p
```

Once the files pops up I can use n and p to navigate between the 2 files. Where n is next and p is previous

```
q
```

I then used the q key to quit and exit out of the file that I am on. This brought me back to the terminal.