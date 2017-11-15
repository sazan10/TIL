# TIL(Today I Learned)
A minimal repo for my #TIL stuffs related to programming, technology and anything.

-----
-----


## Nov 13, 2017

Today I learned different things about Linux.

### Summary of the things I learned
 1. The linux kernel
 2. SHELL
 3. File System Hierarchy standard in Linux
 4. Different commands in Linux like mkdir, tar, chmod, diff, top, uptime, pwd, ls, whoami...

```bash
The ubuntu puzzle was really fun and engaging yet informative.
```

-----
-----


## Nov 14, 2017

Learned about git

### Summary of the things I learned
 1.  Creating Git repository (git init)
 2.  Checking git status (git status)
 3.  Staging the modifications in git (git add file_name)
 4.  Committing (git commit -m 'message')
 5.  Cloning git repository (git clone url)
 6.  Branching out (git branch branch_name, git checkout -b branch_name)
 7.  Switching between branches (git checkout branch_name)
 8.  Merging branches (switch to master and git merge branch_name)
 9.  Pushing git repository (git push origin master)
 10. Pull git repository (git pull url)
 11. Setting url of git repo
 12. Connecting to github with ssh key
 ``` bash
 Thus, different git operations were learned and also got familiar on writing TIL.
 ```

-----
-----


## Nov 15, 2017
Learned python

### Summary of the things I learned
 1.  Using conditions, loops(for x in range(a,b)), functions(def), comments(#, ''')
 2.  Default values for arguments
 ``` bash
 3.  Using Multiple arguments
      def function_name(var="value"):
 ```
 ``` bash
      def function_name(*args):
 ```
 4.  Unpacking arguments
 ``` bash
      def function_name(int, string, string):
      list=[1, "name1", "name2"]
      function_name=(*list)
 ```

 5.  Sets(a={}), dictionaries(a={'key':'value'})
 ``` bash
      to show dictionary content
      for k, v in dic.items()
       print(k+","+v)
 ```
 6.  Modules
 
      while importing modules python2 showed error so needed to switch to python3
 
 7.  Downloading image fromweb using urllib.request module
 8.  Reading and writing files
 ``` bash
      Writing file
      file=open("file_name.txt","w") // creating file and opening in write mode
      file.write("content to write")
      file.close()

      Reading file
      file=open("file_name.txt","r") // creating file and opening in write mode
      text=file.read()
      print(text)
      file.close()

 ```
 9.  Downloading Files from the Web
 ``` bash
      Downloaded csv file from the web and saved it in local disk
 ```
10.  Creating a web crawler
11.  Exception Handling
``` bash
      try:
       expression
      except type_of_exception:(ZeroDivisionError, ValueError, empty for all types)
```
12.  Objects and Classes
``` bash
      class Class_name:
       var=1
       def function_name(self):
        self.var+=1
```
13.  Initialization at object creation
``` bash
      def __init__(self, *args)
       self.args=value
```

-----
-----


## Nov 16, 2017
