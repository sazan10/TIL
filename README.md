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

 ## Dec 4, 2017
 Starting of MySQL
 1. Adding root password 
```
	mysqladmin -u root password "password_exp";
```
 2. The various commands used in mysql with their functions are: 
```
	SHOW DATABASES; [To view databases]
	USE databases_name; [To change database]
	SHOW TABLES; [Displays tables in database]
	SHOW COLUMNS FROM table_name; [Displays columns from table]
	SELECT a,b,c FROM table_name WHERE column='value';
	CREATE DATABASE database_name;
```
 3. Setting users and privileges
```
	USE mysql;	
	INSERT INTO user (host, user,password,select_priv,insert_priv,update_priv) values 						('localhost','amatya',password('password'),'n','y','y');
	FLUSH PRIVILEGES;

	mysql -u username -p [to login]

	To Grant all privileges:
	GRANT ALL PRIVILEGES ON *.* TO 'username'@'localhost';

	Delete Users:
	DROP user 'username'@'localhost';
```
4. Datatypes in mysql
``` 
	INT [unsigned-> 0 to 2^32-1    signed-> -2^16 to 2^16-1]
	FLOAT(M,D) display length (M) and number of decimals (D)
	DATE [yyyy-mm-dd]
	CHAR(M) [fixed length(M) string bet 1 and 255 chars]
	VARCHAR(M) [variable length string bet 1 to 255 char]
	BLOB or TEXT- Binary Large Objects usually image or other types of files
```
  
-----

-----


## Dec 5, 2017

MySQL continuation
1 . Creation of table

	CREATE TABLE table_name(column_name column_type);
	
2 . Insert  into tables

	INSERT INTO table_name (field/col_name1,name2,...) VALUES (value1, value2,...)

3 . Select with Grouping and ordering
	
	SELECT * FROM table_name WHERE(YEAR(now()-YEAR(year_field)) < value;
	
	SELECT * FROM table_name ORDER BY field_name ASC LIMIT value;
	
	SELECT * FROM table_name GROUP BY field_name DESC LIMIT value;
	
4 . Comparing Two tables
	
	SELECT field_a, field_b FROM table_a, table_b WHERE table_a.id=table_b.id;
	 
5 . Delete 
	
	DELETE FROM table_name [WHERE clause];

6 . Update

	UPDATE table_name SET field1=value1,field2=value2,... [WHERE clause];
	
7 . Using LIKE
	
	SELECT * FROM table_name WHERE field LIKE "%(ending_seq)"; 

8 . Regex

 Pattern     |Meaning   
-------------|-------------	
^|Beginning of string
$|End of string
.|Any single character
[...]|	 Any char listed bet square brackets
[^...]| Any char not listed bet square brackets
*| zero or more instances of preceding element
+| one or more instances of preceding element
\{n} | n instances of preceding element
\{m,n} | m through n instances of preceding term
	
	SELECT field FROM table_name WHERE field REGEXP 'regex';
	
9 .  Modify Table

	ALTER TABLE table_name DROP field;
	ALTER TABLE table_name ADD field  type;
	ALTER TABLE table_name MODIFY field type;[modify type of column]
	ALTER TABLE table_name RENAME TO new_name;
	
10 . Index and primary key
 Primary key is for uniqueness whereas index doesn't define uniqueness,  and is used to more quickly find rows in the table.

	CREATE [UNIQUE] INDEX index_name  ON table_name (column1, column2, ...);	
	ALTER TABLE table_name ADD PRIMARY  KEY(column_list);
	ALTER TABLE table_name ADD UNIQUE/INDEX index_name (column_list);

11 . Cloning a Table
	
	SHOW CREATE TABLE table1_name \G;
	--create table with same structure after copying
	INSERT INTO clone_table(field1, field2,...) SELECT * FROM table1_name 
	  
12 . Saving data into file
mysql --local-infile=1 -u root -p [enable writing from txt file to table]
	
	SELECT * FROM table_name INTO OUTFILE 'path[txt,csv];
	SELECT * FROM table_name INTO OUTFILE 'path[txt,csv]  FIELDS TERMINATED BY ',' ENCLOSED BY '"' LINES TERMINATED BY '\r\n' ;
	LOAD DATA LOCAL INFILE 'path' INTO TABLE table FIELDS TERMINATED BY ',' ENCLOSED BY '"' LINES TERMINATED BY '\r\n' ;

13 . Using sqldump
	
To dump table from database into file
	
	mysqldump -u root -p database_name table_name > [path]

To dump whole database into file
	
	mysqldump -u root -p database_name > [path]

Importing to databae from file
	
	mysql -u root -p database_name < file_name
	
14 . Import using MYSQLIMPORT

	mysqlimport -u root -p --local database_name path
	mysqlimoprt -u root -p --local --fields-terminated-by="," --lines-terminated-by="\r\n" database_name file_name

15 . Import using LOAD DATA

	LOAD DATA LOCAL INFILE 'path' INTO TABLE table_name; 


-----
-----

 ## Dec 6, 2017
SQL continuation
1 . Accessed localhost database through phpmyadmin

2 . Using IN
	
	SELECT field FROM talbe_name WHERE field [NOT]IN (value1, value2,..); 

3 . Custom Columns
	
	SELECT CONCAT(field1, ' ,', field2) AS new_field FROM table_name;
	SELECT field1, field2, field2-1 AS new_field FROM table_name;
	
4 . Functions
Some functions used in mysql are:
	
	CONCAT(), SUM(), AVG(), UPPER(), SQRT(), COUNT(), MAX() 
	
5 .  SubQueries
	
	SELECT field1 FROM table_name WHERE field2 > (SELECT AVG(field) FROM table_name);
	
6 . Joining tables

	SELECT table1.field1, table1.field1, table2.field1 FROM table1, table2 [WHERE clause] 

![alt text](https://www.w3schools.com/sql/img_innerjoin.gif  "join table")

	SELECT table1.field1, table1.field1, table2.field1 FROM table1 LEFT OUTER JOIN table2 [ON clause] 
	
![alt text](http://www.dofactory.com/Images/sql-left-join.png "left outer join") 

	SELECT table1.field1, table1.field1, table2.field1 FROM table1 RIGHT OUTER JOIN table2 [ON clause] 

![alt text](http://www.dofactory.com/Images/sql-right-join.png "right outer join")

7 . Union 
Works similar to OR but the fields should be same in both the SELECT statements. Using UNION ALL duplicate values can also be displayed.

	SELECT field FROM table_name [WHERE clause]
	UNION
	SELCET field FROM table_name [different WHERE clause] 
	
8 . Full Text Searching

	SELECT field1, field2 FROM table_name WHERE Match(field) Against('+expre -expre' IN BOOLEAN MODE)
	
9 . View
View is a temporary table which is dynamic and updates as soon as data changes
	
	CREATE VIEW AS view_name 
	-- follow up with select statement
	
10 . ACID

Atomicity: All part of transaction fail or succeed together

Cosistency: The database will always be consistent

Isolation: No transaction can affect other transaction

Durability: Once the transaction is commited it wont get lost 

-----

-----

## Dec 8, 2017
1 .Foreign Keys
Foreign keys are keys to link two tables. It is a field in one talbe that refers to primary key in anther table.

	FOREIGN (field) REFERENCES table2(field);
	
MongoDB
1 . Some basic commands are:
	
	--to view databases
	show dbs
	--to switch databases
	use database_name
	--show currently working database
	db

2 . Add user
	
	db.createUser({user:"user_name", pwd:"password", roles:["readWrite","dbAdmin"]});

3 . Create collection

	db.createCollection('collection_name');
	show collections

4 . Insert into collection
	
	db.collection_name.insert({field1:"value", field2:"value2"});
	
5 . Find value in collection
	
	db.collection_name.find({field1:"value"});
	db.collection_name.find().pretty();
	
6 . Deleting collection
	
	db.collection_name.drop();
	
7 . Update collection
	
	db.collection_name.update(json_data_to_udate,json_data_dest[multiple fields]);
	--to update only specific fields
	db.collection_name.update({...},{$set:{...}});
	db.collection_name.update({...},{$inc:{field:incre_value}}):
	
8 . Remove a field

	db.collection_name.update({field:value},{$unset:{field_to_unset:1}});
	
9 . Insert if not found

	db.collection_name.update(json_data_to_udat,json_data_dest[multiple fields],{upsert:true});
	 

10 . Rename field for specific record

	db.collection_name.update({field:value},{$rename:{"old_field_name":"new_name"}});
	
11 . Remove record
	
	db.collection_name.remove({},{});
	
12 . Using AND/OR , less(lt), greater (gt) ,gte,ne,lte
	
	db.collection_name.find({$[and/or]:[{key1:value1},{key2:value2}]}])
	db.collection_name.find({<key>:{$lt:<value>}});
	
13 . Sort
	
	db.collection_name.find().sort({key/field:1/-1});
	
14 . Count, limit 
	
	db.collection_name.find().count();
	db.collection_name.find().limit(value);
	
15 . Iterate through:
	
	db.collection_name.find().forEach(function(arg){print(doc.field)});
	
-----

-----

## Dec 11, 2017
	
1 . To skip :
		
	db.collectionName.find().skip(value);
			
2 . To create, get and drop index :

	db.collectionName.ensureIndex({fieldName:1});
		
	db.collectionName.getIndexes();
	
	db.collectionName.dropIndex({indexedFieldName:1});
		
3 . Aggregation

	db.employees.aggregate([{$group:{_id:"$fieldName",total:{$sum:1}}}]);	
	db.employees.aggregate([{$group:{_id:"$fieldName",MaxAge:{$max:"$Age"}}}]);

4 . Backup and Restore
```bash	
	mongodump;
	mongorestore;
	mongodump --db databaseName
	mongorestore --db databaseName path
	mongodump --db databaseName --collection collectionName
	mongorestore --db databaseName --collection collectionName path
```

5 . Update and insert if not existing

	 db.collectionName.update({fieldName:"toFind"},{fieldName:"toUpdateto with other non updating field"},{upsert : true});

			
6 .  Update multiple data at once
	
	db.collectionName.update({fieldName:"toFind"},{$set:{fieldName:"toUpdateto"}},{multi:true});
			
Advanced Java

1 . Different stages in the life cycle of a thread are:

- New- beginning of life cycle... new thread remains in this state until program starts the thread.
- Runnable- after thread is started... thread is executing its task.
- Waiting- while thread waits for another thread to perform a task. Becomes runnable only when the other thread signals to continue executing.
- Timed waiting- specified interval of time. Becomes runnable if time expires or when the event it is waiting for occurs.
- Terminated- when task is completed or thread terminates.

2 . Thread Priorities
-  min priority(1), max priority(10), default_normal pririty(5)

3 . Creation of thread by implementing a Runnable Interface

- implement run method

		public void run(){}
	
- Instantiate Thread Object

		Thread(Runnable threadObj, String threadName);

- Start a Thread by calling start() method which executes a call to run() method

4 . Creating a Thread by Extending a Thread Class

- Override run() method in available Thread class

		public void run( )
		
- Start thread by calling start() method

5 . Thread Methods
```bash
	public void start()  'Starts the thread and envokes the run() method'
	public void run() 'run method is invoked on the targeted Runnable object'
	public final void setName(Strin g name) 'Changes the name of the thread object'
	public void getName() 'retrieve name of thread object'
	public final void setPriority(int priority) 'Set priority of thread object'
	public final void setDaemon(boolean on) 'true denotes thread as daemon thread'
	public final void join(long millisec) 'block current thread until second terminates or specified time expires'
	public void interrupt() 'interrupts this thread'
	public final boolean isAlive() 'returns true if thread is alive'
```	
	
6 . Static Methods
```bash
	public static void yield() 'current thread yields to another thread of same priority'
	public static void sleep(long millisec) 'current thread blocks for specified milliseconds'
	public static boolean holdsLock(Object x) 'true if the current thread holds the lock on the given Object'
	public static Thread currentThread() 'reference to the currently running thread'
	public static void dumpStack() 'prints the stack trace for the currently running thread, useful for debugging'
	
```	

7 . Factory Pattern
When a method returns one of several possible classes that share a common super class, and the class is chosen at runtime.
	
-----

-----

## Dec 12, 2017
Advanced Java Continuation

1 . Abstract Factory Pattern
Similar to Factory pattern, but everything is encapsulated. Generally the methods are extended/implemented for creating factory of factories. Factory method is a single method whereas abstract factory is an object. Thus, A factory can create objects that derive from a particular base class.An abstract factory can be considered as a factory that creates other factories, and these factories in turn create objects derived from base classes.	

2 . Singleton Pattern
This pattern involves a single class which is responsible to create an object while making sure that only single object gets created. SingleObject class have its constructor as private and have a static instance of itself and the following describes the way to get the only object from the singleton class:

	SingleObject object = SingleObject.getInstance();
	--access the methods
	 object.method;
	 
3 . Builder Pattern
Builder is a pattern used to create complex object using simple objects
    
4 . Iterator Pattern
This pattern is used to get a way to access the elements of a collection object in sequential manner without any need to know its underlying representation. 

5 . MVC(Model View Controller) Pattern
Model represents an object, View represents the visualization of the data that model contains. Controller acts on both model and view. It controls the data flow into model object and updates the view whenever data changes. It keeps view and model separate.

6 . JDBC
The following are the steps required to handle databases:

- Import the packages: packages containing the JDBC classes need to be imported, eg import java.sql.*
- Register the JDBC driver: initialize a driver  to open a communications channel with the database
- Open a connection: Requires using the DriverManager.getConnection() method to create a Connection object., physical connection
- Execute a query: object of type Statement for building and submitting an SQL statement to the database
- Clean up the environment:  Requires explicitly closing all database resources

-----

-----

## Dec 12, 2017
Advanced Java 

1 . Generic methods
	
	class Class_name{
	public <T> void funciton_name(T[] x){
		for(T b:x)
			sout}
	-- To call function
	Class_name.<Type>function_name(Type Object)
	
2 . Generic Return Type
	
	public <T extends Comparable<T>> T func_name(T a,T b){
	-- the above method only accepts methods which extends comparable
		T new_ = a;
		if(a.compareTo(b) >0)
			new_=b;
		return new_;}
		
2 . Using Generic in Class

	class Bottle<T>
	{public [T/Object] liquid;}
	
	{	Water w= new Water();
		Bottle <Water>b = new Bottle<>();
		w = [(Water)] b.liquid; }
	-- Here, typecasting is needed if 'Object' type is used and not for generic
	
3 . Bounded Generic 
Used to confine the generic type to certain group.
	
	class Class_name<T extends R>
	
	-- for multiple bounds, the concrete type is placed first
	class Class_name<T extends R & S> 
	-- here, R is concrete class and S may be an interface
	
4 . Inheritance and subtyping
	
	class Class_A<T> extends Class_B<T>{}
	Class_B<Type> a = new Class_A<Type>;
	--Here, the Type argument should be same for both

 5 . Wildcards
 
 	public void function_name(Class_name<?> name){}
 	--Lower/Upper Bounded Wildcards
 	public void function_name(Class <? extends Parent> name){}
 	public void function_name(Class <? super Child> name){}
 	
 When working with lists, Generic can be used to add to list while wildcards show error.