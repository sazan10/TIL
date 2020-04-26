### Redux using useSelector
```
	const value= useSelector(state=> state.meals.meals)
```

Redux values can be only used in functions or classes but sometimes we may need it in navigationOptions. To pass redux values to navigationOptions use setParams in function.
```
	props.navigation.setParam({mealId: value.mealTitle})
	#retrieve it in navigationOptions using
	props.navigation.getParam('mealId');
```
### Dispatching redux functions
```
    const dispatch = useDispatch();
    const toggleFavoriteHandler = useCallback(
        () => {
            dispatch(toggleFavorite(mealId));
        }, [dispatch, mealId]);
    useEffect(() => {
        props.navigation.setParams({ toggleFav: toggleFavoriteHandler });
    }, [toggleFavoriteHandler]);
```