`cd` command, with 3 examples:

**First example, with no arguments:** 
```
[user@sahara ~]$ cd
[user@sahara ~]$
```
*The working directory was:* /home
*Explanation of output:* `cd` stands for change directory, but no arguments are given so it does not change to anything.
*Error?:* Not necessarily an error but it will not have an effect.

**Second example, with a path to a directory:**
```
[user@sahara ~]$ cd lecture1
[user@sahara ~/lecture1]$ 
```
*The working directory was:* /home
*Explanation of output:* It changed the working directory to /home/lecture1
*Error?:* None

**Third example, with a path to a file:**
```
[user@sahara ~/lecture1/messages]$ cd vi.txt
bash: cd: vi.txt: Not a directory
```
*The working directory was:* /home/lecture1/messages
*Explanation of output:* `cd` changes the directory, but `vi.txt` is not a directory so it cannot do so.
*Error?:* The error was given because the text file given as an argument is NOT a directory.

`ls` command, with 3 examples:

**First example, with no arguments:**
```
[user@sahara ~/lecture1/messages]$ ls
en-us.txt  es-mx.txt  vi.txt  zh-cn.txt
```
*The working directory was:* /home/lecture1/messages
*Explanation of output:* `ls` is the command to list the files within a directory, so as expected it listed the files inside the working directory.
*Error?:* No error

**Second example, with a path to a directory:**
```
[user@sahara ~]$ ls lecture1
Hello.class  Hello.java  messages  README
```
*The working directory was:*  /home
*Explanation of output:* `ls` is the command to list files within a directory, so as expected it listed the files in the working directory.
*Error?:* None

**Third example, with a path to a file:**
```
[user@sahara ~/lecture1/messages]$ ls vi.txt
vi.txt
```
*The working directory was:* /home/lecture1/messages
*Explanation of output:* It listed the singular file, because the file is not a directory and only contains itself.
*Error?:* None

`cat` command, with 3 examples:

**First example, with no arguments:**
```
[user@sahara ~/lecture1/messages]$ cat

```
*The working directory was:* /home/lecture1/messages
*Explanation of output:* It will return nothing initially, and then for any input thereafter, it will return the same output.
*Error?:* All input in terminal is duplicated, and this is because cat was not given an argument.

**Second example, with a path to a directory:**
```
[user@sahara ~]$ cat lecture1
cat: lecture1: Is a directory
```
*The working directory was:* /home
*Explanation of output:* `cat` will concatenate a file and displat it, but /home/lecture1 was a directory so there is no file to print.
*Error?:* lecture1 is a directory and it cannot be printed

**Third example, with a path to a file:**
```
[user@sahara ~/lecture1/messages]$ cat zh-cn.txt
你好世界

```
*The working directory was:* /home/lecture1/messages
*Explanation of output:* It returned the contents of the zh-cn.txt file
*Error?:* None

