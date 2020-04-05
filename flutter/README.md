# FLUTTER

## Flutter Architecture
* UI as code : Build a widget tree. 
* NO drag and drop but only code.
* Everything is a widget

## Create Flutter Project 

```
		flutter create project_name
```

## Folder Structure
#### .idea Folder
Holds configuration for android studio.

#### android Folder
flutter compiled code will be injected to this folder for android project.

#### build Folder
Holds output of the flutter application. Automatically done while deployment.

#### ios Folder
flutter compiled code will be injected to this folder for android project.

#### lib Folder
Most important folder where 99% of work is done. Coding

#### test Folder
For writing test codes.

##### Wont be using rest of the files, they are used by flutter for internal config. Need to use pubspec.yaml file for fonts/images, third party packages. pubspec.lock is not used. It is a detailed file for all the dependencies generated automatically based on pubspec.yaml file

### Some VS Code Trick
```
			ctrl+p for quick open
			ctrl+shift+\ to match corresponding paranthesis
			ctrl+shift+m to see errors
			ctrl+shift+o to find symbols in file
			ctrl+. to extract method
```
### Code Structure
* main() function is the entry point for dart application which is first automatically called by flutter.

* Dart is type strict so it needs explicit datatype if not it assumes dynamic datatype.

* Create variable using var(dart considers the value on the right and initializes accordingly) , double


### Rudimentary Example
```
import 'package:flutter/material.dart';

void main (){
  runApp(MyApp());
}

class MyApp extends StatelessWidget{
@override
  Widget build(BuildContext context)
  {
    return MaterialApp(home:Text('Hello'),);
  }
}
```
Here main function is run automatically first by flutter which then looks for the runApp function given by flutter from material.dart which receives MyApp class instance.  MyApp is a child, i.e. it inherits StatelessWidget which must include a build method which can have argument. buildcontext need not be defined but just defined as dart automatically handles it and context generally consist of metadata for the corresponding widget, its position and so on. **Here BuildContext, Material, Text are objects. Flutter looks for build method to render things so, it should return a widget. Here, name:Text('hello') is a named argument.

#### Example of constructor in Dart

```
	class Person{
	int age;
	String name;
	Person({int age, String inputname}){ //Person({@required int age ...
	this.age=age;
	name= inputname;
	}
	
	var p1= Person(inputName:'sdfd",age:34)
```
@required if is used flutter shouts that arguments are necessary.


Alternative shortcut
```
Person(this.age,this.name)
```
Need to rename the named argument to name:'sdfd'

#### Scaffold 
It is used to create base page. It consists body, appbar, drawer, floating actionbutton and so on.

### NOTE USE CTRL+SPACE TO KNOW AVAILABLE ARGUMENTS WITHIN EACH WIDGET/OBJECT

```
Ctrl+Shift+i 
```
Use this to format document in vs code.

#### The properties can be made private by using '_' in front of each property whether it be class, method or variables.
```
	_MyApp(){
		var _value;
		}
```

#### SetState
setState calls the build method again which rebuilds the widget tree but does not rerender the entire tree but only the changed ones.


 **Note:It is generally a good practice to use only one widget file per**
 	
 **In case of stateless widget the build is not rerendered as it does not expect any change to variables so generally all variables are defined final but it can be rerendered on changing input value. But in stateful widget even state change can rerender.** 
 
#### Creating multiple constructors in dart
 Use '.' to create multiple constructors
 ```
 	const EdgeInsets.all():
 	const EdgeInsets.only()
 ```
 
 
#### Passing functions to Widgets
```
	 Answer(_answerQuestion);
	 
	 
	 class Answer extends StatelessWidget {
  		final Function selectHandler;
  		Answer(this.selectHandler);
  		...
  		}
```

#### Working with map in dart

```
    var question = [
      {
        'Question': 'What\'s your favourite color',
        'Answers': ['Blue', 'Green', 'Red', 'Black']
      },
      {
        'Question': 'What\'s your favourite animal',
        'Answers': ['Dog', 'Cat', 'Rabbit', 'Guinea']
      },
      {
        'Question': 'What\'s your favourite food',
        'Answers': ['Pizza', 'Momo', 'Burger', 'Sandwich']
      },
    ];
    
    Then inside children of body:
    
          ...(question[_questionIndex]['Answers'] as List<String>).map((f) {
              return Answer(_answerQuestion, f);
            }).toList(),
    
```
Here, by default dart does not recognize question[_questionIndex]['Answers'] as List of strings so we need to specify it explicitly and map it. The return statement is to be a widget since the children of body can only be a widget. But we simply cannot just return as it returns, but need to return it as a widget list(using toList) and then finally spread it in the body array rather than creating a new one.

#### const vs final
Final can be assigned at runtime but const needs immediate value

```
 	final a; 	
	a=input;
 	cont a1=const [1,2]
 	var a2=const[1,2]
 	var a3=[1,2]
```
Here, it allows a3.add(4) but not a2.add(4). Obviously it is not possible for a1 as well. We can also change assigned values for a2 and a3 but not for a1. 

```
Note: Column takes size of its broadest child and Text takes size necessary or its parent(Container which can be modified as necessary)
```

#### Column/Row vs Container
Container takes exactly one chlid widget whereas Column/Row takes multiple child widgets.  
Container has rich alignment and styling options but not in row/column.
Container has flexible width(eg child width, available width,...). Column takes full availabe height and width for row.
For stylin use container and if widgets sit next to/above use column/row.

```
Note: When accessing/modifying state/method of different stateful components, the current component should also be stateful and the values of other stateful component can be accessed using widget while executing. eg. widget.add()
```

### Dynamically fit widgets
To dynamically fit widgets use MediaQuery.of(context).size.height to get height of full screen and fractionally divide it among widgets. Also for children widgets use LayoutBuilder to constrain the children to the available space.
```
		return LayoutBuilder(
			builder:(ctx, constraints)
			{
			return Column(children:.....
			height:constraints.maxHeight*0.7
			
			})) 
```

### Forcing App to run only on portrait mode
In main instead of just returning runApp add:
```		
		import 'package:flutter/services.dart';
		SystemChrome.setPreferredOrientations([
			DeviceOrientation.portraitUp,
			DeviceOrientation.portraitUp,
			]);
		runApp(MyApp());
```

Note: "context" cannot be passed into initState as initstate is called very early even before context is created so if needed use didChangeDependencies.

### Provider(Same as redux)
Need to create class and surround the root app with provided. notifylisteners and add listeners.
			