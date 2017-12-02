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
   

-----
-----
 
## Nov 21, 2017
Continuation of Core Java
1. Access Specifiers
 ```
 	public => can be accessed from anywhere
	protected => same package/child
	private => only in same class
	no specifier => same package/ no child
 ```
 2. Polymorphism
    A child class can be used anywhere in place of a parent class, such that the parent can access the overridden methonds of c       	  child. Child can be used in place of parent but reverse is not true.
    
 3. Generic class
    A generic type or method allows to operate on objects of various types while providing compile-time type safety. 
 
 4. Abstract
    For base classes which are inherited and not used to make objects/instantiate. For every abstract methods, implementation        	should be contained in children.
    Abstract is extended whereas interface is implemented. Abstract may contain codes but interface has only definitions, no 	                     	 implementation.
    
 5. Serialization
    Serialization enables us to represent an object as a sequence of bytes  and to write objects to files. Th file can be read 	
    and deserialized to represent the object.
 
 6. Started the Java Core, JSON parsing assignment. Was able to parse the JSON file and obtain the data as objects.
 
-----
-----
 
## Nov 22, 2017
Continuation of Core Java and initiation of OOP
 1. Completed the JSON parsing assignment.
 
 2. Association(OOP)
    Describesany kind of working relationwith no ownership, no effect on life cycle.
 
 3. Aggregation
    Relationship in whichone object belongs to another object, but still independent. Independent life cycle but there exists       	ownership.
  
 4. Composition
    If parent destroyed children cease to exist.
 
 5. Polymorphism
    Same operation can be invoked on objects of different classes and they wil all perform in their own way.
    
 6. SOLID
 
    S- Single Responsibility => There should never be more than one reason for a class to change.
    
    O- Open/Closed => A module should be open for extension but closed for modification
    
    L- Liskov Substitution => Subclasses must be usable as their bas classes
    
    I- Interface segregation => Many client specific interfaces are better than one general purpose interface.
    
    D- Dependency Inversion => Depend upon abstraction, do not depend uponconcretions.
    
-----
-----
 
## Nov 23, 2017
Continuation of OOP
 1. Completed OOP reading material
 2. Started OOP assignment and performed CRUD operation
 
-----
-----

 ## Nov 24, 2017
Continuation of OOP
 1. Continued OOP assignment 
    
-----
-----

 ## Nov 27, 2017
Started Data Structure and Algorithm
 1. Learnt Bubble sort, selection sort and insertion sort with their time(O(n^2)) and space complexity.
 ```
 	logn(n) <= n^(1/2) <= nlog(n) <= n^2 <= n^3 <= 2^(n) <= n! 
 ```
    Insertion sort is relatively good for small lists, particularly sorted lists. Bubble sort is very inefficient whereas
    selection sort is better than bubble sort. In selection sort the running time is independent of ordering of elements.
 	 
-----
-----

 ## Nov 28, 2017
Continuation of DSA
 1. Learnt and implemented Linked list, stack and queue. In linked list search is slow {O(n), O(log(n)) in sortedArrays},
    insertion is fast { O(1), O(n) in sorted arrays} and deletion is fast { O(1), O(n) in sorted arrays}
 
-----
-----

  ## Nov 29, 2017
Continuation of DSA
 1. Learnt Mergesort, recursion and tower of hanoi 

-----
-----

  ## Nov 30, 2017
Continuation of DSA
 1. Binary Tree and Binary Search Tree
    In binary tree, a node contains only two child at max, with smaller on the left and greater on the right. On the other hand 
    in case of binary search tree the nodes are arranged in ordered, thus it is also called ordered binary tree.
 2. Tree Traversal
    a. In order
       traverse left sub tree, then visit root and finall the right sub tree.
    b. Pre order
       Visit root, traverse left sub tree and finally the right sub tree.
    c. Post order
       Left, right and root.

-----
-----

  ## Dec 1, 2017
Continuation of OOP
 1. Learnt and implemented shell sort and quick sort. Completed the DSA, first course.
 
-----
-----

  
  
