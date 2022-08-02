# LinuxAssignment

### Q1 How do we identify child process & parent process using command & how do we interpret whether child has a relation with the parent from the output?
Ans : we can identify child process & parent process using ps command.
```bash
ps -He
-e : Select all processes.
-H : Show process hierarchy (forest).
```
Child process will show in indentation of parent process and parent will on the top of child process.

### Q2 List the command to check whether a process is multi threaded or single threaded.
Ans : command is 
```
ps -eLf
-L	Show threads, possibly with LWP and NLWP columns.
-e	Select all processes
-f	Do full-format listing
```
check NLWP column to see weather a process is multi threaded or single threaded.

### Q3  What are the different commands to copy a file from one location to another, give with example
Ans : cp command is use to cp one file or directory to other location.

Example: we want to copy file test to p1 directory then we should follow this step.
```bash
cp test ./p1/
```

### Q4 A file is getting updated in real time on the server( having linux distribution), which is probably a log file, how do we check the updated content of the file in real time.

Ans: first create one which get update every second for that 
```bash
for run in {1..100000}; do `echo "hello+$run" >> test.txt`; done
```
this will create test.txt and it will append new data at the end.Open another tab in terminal and check the contents of the file getting updated by this command.
```bash
cat test.txt | tail -n 10  --> give last ten line of test.txt

or

tail -f test.txt --> to see live change of test.txt
```

### Q5 How do you list all the files of a directory without listing . & .. on the output.
Ans: command is
```bash
ls
```
### Q6 print only the value of the memory on the output which can be used by new applications to be executed without the need of swapping.(Note: only the value of such memory is expected in the output).

### Q7  "Unix stands for UNiplexed Information and Computing Service, Unix is written in C"Use the above string to append it to a file ( say sample.txt) 10 times & then print the number of occurrences of "Unix word" in that file.

Ans : 
```bash
for run in {1..10}; do `echo "Unix stands for UNiplexed Information and Computing Service, Unix is written in C" >> test.txt`; done  &&  cat test.txt | grep -o "Unix" | wc -l
```
### Q8 Create below directory structure in a single execution of command
Ans : ```bash
mkdir -p p0/{p1/p2/{p3/p5/p9,p4/p5/p9},p6/{p7/p9,p8/p9}}
```

### Q9 Copy the file used in Question#7 (i.e. sample.txt) to p9 directory(s) of Question#8 As there are multiple p9 directories so sample.txt should exist inside all those p9 directories.Write command for above question where copy operation should take place in single execution of command.
Verify your output using tree p0 command

Ans: ```bash 
for dir in $(find -name p9); do cp test.txt $dir; done
```




