# Lab Report 3
## Find command

1. **-name**
The `find -name` command in bash is a useful way to find files or directories that match a certain or specific pattern.
Example 1:
``` 
cs15lsp23lx@ieng6-203]:technical:154$ find 911report/ -name "*3*"
911report/chapter-13.1.txt
911report/chapter-13.2.txt
911report/chapter-13.3.txt
911report/chapter-13.4.txt
911report/chapter-13.5.txt
911report/chapter-3.txt
```
In this example, I'm looking for all the files in 911report/ that have a "3" in the name. There are a significant amount of other files in 911report/ but this command specifically searches for those that contain "3".

Example 2:
```
cs15lsp23lx@ieng6-203]:technical:166$ find plos/ -name "*journal*"
plos/journal.pbio.0020001.txt
plos/journal.pbio.0020010.txt
plos/journal.pbio.0020012.txt
plos/journal.pbio.0020013.txt
```
*The output was shortened for conciseness*

In this example, I'm looking through all the files and plos/ and asking the terminal to return to me all the files that have "journal" in the name, as shown above.

2. **-type**
The `find -type` command is useful for finding files of a specific type. There are several additional modifies for this option, such as `-f`(searches for regular flies) `-c`(searches for character devices) and so on.
Example 1:
```
cs15lsp23lx@ieng6-203]:technical:169$ find government/ -type f
government/About_LSC/CONFIG_STANDARDS.txt
government/About_LSC/Comments_on_semiannual.txt
government/About_LSC/LegalServCorp_v_VelazquezDissent.txt
government/About_LSC/LegalServCorp_v_VelazquezOpinion.txt
government/About_LSC/LegalServCorp_v_VelazquezSyllabus.txt
```
*Output shortened for conciseness*

In this example, through the use of `find -type f`, I am searching through the government/ directory in search of all regular files, which are to be shown by the terminal.

Example 2:
```
find -type d
.
./911report
./biomed
./government
./government/About_LSC
./government/Alcohol_Problems
./government/Env_Prot_Agen
./government/Gen_Account_Office
./government/Media
./government/Post_Rate_Comm
./plos
```

In this example, I used `find -type d` in the technical/ directory to search for and have the terminal show all it's subdirectories.

3. **-size**
The `find - size[+/-]n[cwbkMG]` command is useful for searching for and outputting files that are either larger or smaller than the search criteria you are looking for. The [+/-] informs whether or not you want to look for files that are larger or smaller, respectively, than the criteria given. The n[cwbkMG] is the size (n is for bytes, cwbkMG is for size of the unit. 
Example 1:
```
[cs15lsp23lx@ieng6-203]:technical:201$ find -size +500b
./911report/chapter-13.4.txt
./911report/chapter-13.5.txt
./911report/chapter-3.txt
./government/Gen_Account_Office/Statements_Feb28-1997_volume.txt
./government/Gen_Account_Office/d01591sp.txt
```

In this example, I used `find -size` to search through technical/ and look for files larger than 500 bytes, denoted by the `+500b` modifier. In technical/, there are 5 of such files.

Example 2:
```
cs15lsp23lx@ieng6-203]:technical:210$ find -size -3b
./plos/pmed.0020191.txt
./plos/pmed.0020226.txt
```

In this example, I used `find -size` to search for files smaller than 3 bytes, as shown by the `-3b` modifier, and found that there are only 3 of these files.

4. **-exec**
The `find -exec` command runs a command on all the files that are found during the search. More specifically, the command runs: `find {criteria} -exec {command}/;`, where "criteria" is the parameters that `find` uses to search for files, and "command" is the action done onto all files that result from that search. This command is useful if you need to run a command on a large number of files that share a criteria.
Example 1:
```
[cs15lsp23lx@ieng6-203]:technical:211$ find -size -3b -exec rm {} \;
[cs15lsp23lx@ieng6-203]:technical:212$ find -size -3b
```

In this example, I used `find -size -3b -exec rm {} \;` to  search for all files that are less than 3 bytes and delete them. The follow-up command, which is identicial to the command run in the previous example, is done to illustrate that those files which used to appear in the terminal upon output no longer exist, highlighting the success of the previous command.

Example 2:
```
[cs15lsp23lx@ieng6-203]:technical:223$ find . -name "*.txt" -type f -exec grep "party" {} \;
    Between 9:15 and 9:30, the staff was busy arranging a return to Washington, while the President consulted his senior advisers about his remarks. No one in the traveling party had any information during this time that other aircraft were hijacked or missing. Staff was in contact with the White House Situation Room, but as far as we could determine, no one with the President was in contact with the Pentagon. The focus was on the President's statement to the nation. The only decision made during this time was to return to Washington.
                down the size of the traveling party. The President's military aide, an Air Force
                for security reasons was taped and not broadcast live, and the traveling party
                responsible party.
```
*Output shortened for conciseness*

In this example, I used the `-exec` option to print out in the terminal all the lines in all the ".txt" files in technical\ that contain the word "party." The `-name "*.txt"` clarifies the criteria of the search to be all files that match the pattern of being a ".txt" file, the `-type f` modifier makes sure the output are all files, and finally, the `-exec grep "party"` option searches through all the files that were found as a result of the search for lines that contain the word "party" and print it to the terminal.
This final example was a great way to show how all the options of a command in bash can work together to accomplish highly specific searches and tasks.

> All commands, options, modifiers, and behaviors demonstrated in the above lab report, if not previously known from lecture materials, came from interacting with ChatGPT. I asked for options for the `-find` command, asked for it to elaborate and for examples, then tried myself on technical/.
