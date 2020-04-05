#### Saga
For saga need to define a saga file where instead of using promise to make request use yield and assign it to a variable. Then, in actions file of reducer add a function to trigger action to trigger saga where a listener using takeevery will execute once the action type is detected.Add saga in index.js sagaMiddleware.run(watchComponents);


#### hooks
Hooks can be used to replace classes/containers and using only components/functions we can change data/states lifecyle hooks/methods to cause rerendering. 
```
	const [value_name, function_name]= useState('')
	<input value={value_name} onChange={event=>{function_name(event.target.value)}};/>
```
However, if we use object states then we need to use inner function to assign previousState as well since unlike in container/stateful class here only the specific states are updated without keeping others intact.


UseEffect runs after every render cycle, so can be considered equivalent to componentDidMount but only when second parameter is empty array. We can also use an array of hook state on whose value the reredering depends as well. If not it may rerender foreover as it tries to detect changes and update state concurrently over and over.

When passing a setStateFunction to children we may require to surround the handler function with useCallback else it may result in infinite looping. For example for search filtering, when using <Search> in <Ingredients> and executing handler



Search.js

	const {onValueType}=props;
	const [state_name,function]=useState('');
	
	
	  useEffect(() => {
		[perform side effects, http requests]
		onValueType(ingredients_para);
		}, [enteredFilter, onLoadIngredients]);

Ingredients.js
	
	<Search onValueType={this.handler}/>
	const handler=useCallback(ingredients_para)=>{
	setUserIngre(ingredients_para));},[]);



