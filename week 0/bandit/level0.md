you need to ssh into the server 
ssh bandit0@bandit.labs.overthewire.org -p 2220
ssh username@ip - portnumber(p) 2220

==6y2kwnwK6grgvwvpvLaa2T1cpFEKOhNR==

level1- 2
==PK8fYLZg2hnHSz83plBL1iEPKdD3QToB==
pwd is in - (dashednamed file) 
direct cat cmd will not work 
it leads to options rather than reading the filename 
so use cat ./- (using relative path prefix )

level 2-3
==7ZZ2LFrykP2zEyvBl4m3clcL7tGYJPME==
pwd is in filename:  --spaces in this filename --
you cannot use cat command directly because linux cmnd system will view it as an argument when you try :
cat -- spaces in this finename --
rather
try : 
cat ./--spaces\ in\ this\ filename-- 
backward slash \ will tell the commnad to treat the spaces as a literal character 

level 3-4

==xzTXq1rDJQVVAzdv5cHq1TQytTWufAMq==

pwd is hidden inside the `inhere` directory in a hidden file

use `ls -a` to show hidden files

then use `cat ./...Hiding-From-You` to read it

level 4-5

==6C7h9GD8M6ai5nr7wo1RonrzFjj9yIrG==

pwd is in the only **ASCII text** file among the files in `inhere`

use `file ./*` to check what type each file is

`file ./*` is used because filenames start with `-`, so `file *` treats the first `-` as an option

the password was in `./-file07`, so use `cat ./-file07` to read it

level 5-6
==pXa26xhMWaC2SvDotA4r9EgZkulOeSBW==

pwd is hidden somewhere inside `inhere`, and the file is **1033 bytes** in size

use `find * -type f -size 1033c` to find the file

the file was `maybehere07/.file2`, so use `cat ./.file2` to read the password