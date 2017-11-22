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
 

```
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
 ``` 
 Thus, different git operations were learned and also got familiar on writing TIL.
 ```

-----
-----


## Nov 15, 2017
Learned python

### Summary of the things I learned
 1.  Using conditions, loops(for x in range(a,b)), functions(def), comments(#, ''')
 2.  Default values for arguments
 ```
      def function_name(var="value"):
 ```
 3.  Using Multiple arguments
 ``` 
      def function_name(*args):
 ```
 4.  Unpacking arguments
 ``` 
      def function_name(int, string, string):
      list=[1, "name1", "name2"]
      function_name=(*list)
 ```

 5.  Sets(a={}), dictionaries(a={'key':'value'})
 ``` 
      to show dictionary content
      for k, v in dic.items()
       print(k+","+v)
 ```
 6.  Modules
      While importing modules python2 showed error so needed to switch to python3
 
 7.  Downloading image fromweb using urllib.request module
 8.  Reading and writing files
 ``` 
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
      Downloaded csv file from the web and saved it in local disk
 
10.  Creating a web crawler
11.  Exception Handling
``` 
      try:
       expression
      except type_of_exception:(ZeroDivisionError, ValueError, empty for all types)
```
12.  Objects and Classes
``` 
      class Class_name:
       var=1
       def function_name(self):
        self.var+=1
```
13.  Initialization at object creation
``` 
      def __init__(self, *args)
       self.args=value
```

-----
-----


## Nov 16, 2017
Python Continuation

### Summary of the things learned today
1.  Inheritance using Python
 ```
      class A():
        content
      class B(A):
 ```
2.  Multithreading
 ```
     import threading
     class A(threading.Thread):
       def run(self):
	 content
     x=A(name="s") //threading.currentThread().getName() in run
     x.start()
 ```
3.  Developed a Word Frequency Counter
4.  Tuples, Zip, Lambda
 ```  Tuple
      first,*mid,last = [1, 2, 3, 4, 5, 6, 7, 8]
      
      Zip
      zip(first_list,second_list)   
      
      Lambda
      a= lambda x: x*7 
      a(5)
 ```
5. Image transformation, cropping, combining, channelling filtering using Pillow
6. Storing value as byte data using struct
7. Map
 ```
      in=[1,2,3,4,5]
      def doub(a):
        return a*2
      li=list(map(doub,in))
 ```
8. Dictionary Multiple Key Sort
 ```
      for x in sorted(object_name, key=itemgetter('object_property1','object_property2'):
 ```
9. Sorting Custom objects
 ```
      for user in sorted(users, key=attrgetter('sort_by_object_property')):
 ```

-----
-----
 
## Nov 17, 2017
Python Continuation

Completed the linear regression assignment using normal linear regression and gradient descent:
```
https://github.com/sazan10/Linear_Regression-Python-Assignment-.git
```

-----
-----
 
## Nov 20, 2017
Started Learning Core Java
1.  Array 
 ```
 	int [] value = new int[3];
 ```
2.  Multidimensional Array
 ```
 	int [] [] g = { {1,2,3,},{4,5,6} };
 ```
3. Static and final
   The static variables and methods are for the class as a whole and is shared whereas final is for constants.
   
4. String builder 
 ```
 	StringBuilder s = new StringBuilder("");
	s.append("");
	s.toString();
 ```
5. Interface
   Contains only definition and no implementations, the inheriting classes implements the methods.
   A class can only extend one parent but implement multiple interfaces.
