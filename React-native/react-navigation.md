### React Navigation
Ref: <a> https://reactnavigation.org/docs/4.x/getting-started </a> 

```
	npm install --save react-navigation
	expo install react-native-gesture-handler react-native-reanimated react-native-screens react-native-safe-area-context @react-native-community/masked-view
	# For version 4 also need
	npm install --save react-navigation-stack

```

### Creating Stack Navigator
Stack navigators are essential to create stacks for storing location to enable back buttons
```

import { createStackNavigator } from 'react-navigation-stack';
import { createAppContainer } from 'react-navigation';
import CategoriesScreen from '../screens/CategoriesScreen';
import CategoryMealScreen from '../screens/CategoryMealScreen';
import MealDetailScreen from '../screens/MealDetailScreen';

const MealsNavigator = createStackNavigator({
    Categories: CategoriesScreen,
    CategoryMeals: {
        screen: CategoryMealScreen //same as others, long form
    },
    MealDetail: MealDetailScreen
})

export default createAppContainer(MealsNavigator);
```
In App.js
```
  return (
    <MealsNavigator />
  );
```
### Simple Naviation using button	
```
   <Button title="Go to Details" onPress={() => {
                props.navigation.navigate({
                 routeName: 'MealDetail',
                     params: {
                                categoryId: itemData.item.id
                            } #used to pass params to next screen ie MealDetail
                  })
            }} />
```
To read Params from MealDetail ie next screen use:
```
    const catId = props.navigation.getParam('categoryId');
```
* Can also use <b>props.navigation.push('MealDetail') </b>. The advantage being it can route to same page but navigate cannot.
* can use <b>.goBack() or .pop() </b> to return to previous page pop being useful only in stack navigator.
* use popToTop() to go to root screen.
* to navigate without back option like in login screen use .replace('Catekde')

### Change Header title, style
Event js function is an object and we can add attributes to js functions as below where CategoriesScreen is a function
```
CategoriesScreen.navigationOptions =navigationData =>{
    headerTitle: "Meal Categories",
    headerStyle: {
        backgroundColor: Platform.OS === "android" ? Colors.primaryColor : ''
    },
    headerTintColor: Platform.OS === "android" ? 'white' : Colors.primaryColor
}
```
Using navigationData.navigation.getParam() we can also extract parameters as in mainfunction.

### Adding some default configurations to every screen
Add the contents in navigator as:
```
{
    mode: 'card',
    defaultNavigationOptions: {
        headerStyle: {
            backgroundColor: Platform.OS === "android" ? Colors.primaryColor : ''
        },
        headerTintColor: Platform.OS === "android" ? 'white' : Colors.primaryColor
    }
```
### Using native controllers ie fragments and ui view controller for navigation
Install react-native-screens
```
	npm install --save react-native-screens
```
Use it after importing it in App.js
```
	import {enableScreens} from 'react-native-screens';
	enableScreens();
```
No difference seen but behind the scenes it is more efficient.
### Adding Header Button
In navigationOptions use:
```
        headerTitle: 'dfdf',
        headerRight: () => <Text>FAV!</Text>
```
To add buttons in headers
* Install header button package
``` 
npm install --save react-navigation-header-buttons
```
* Create a custom header button component:
```
import React from 'react';
import { Platform } from 'react-native';
import { HeaderButton } from 'react-navigation-header-buttons';
import { Ionicons } from '@expo/vector-icons';
import Colors from '../constants/Colors';

const CustomHeaderButton = props => {
    return <HeaderButton {...props}
        IconComponent={Ionicons}
        iconSize={23}
        color={Platform.OS === 'android' ? 'white' : Colors.primaryColor} />

}

export default CustomHeaderButton;
```
* Apply the Created Headerbutton in navigationOptions
```
import HeaderButton from '../components/HeaderButton';
import { HeaderButtons, Item } from 'react-navigation-header-buttons';
        headerRight: () => (
            <HeaderButtons
                HeaderButtonComponent={HeaderButton}>
                <Item
                    title="Favorite"
                    iconName="ios-star"
                    onPress={() => console.log("fav")} />
            </HeaderButtons>)
```

### Tabs Based Navigation
Install react-navigation-tabs for v4 else import it from react-navigation for v3
```
	npm install --save react-navigation-tabs
```
Use it in Navigator js
```
import { createBottomTabNavigator } from 'react-navigation-tabs';

const MealsFavTabNavigator = createBottomTabNavigator({
    Meals: MealsNavigator, #Needs to be navigator to count into affects Stack navigation
    Favorites: FavoritesScreen
});
export default createAppContainer(MealsFavTabNavigator);
```
Here, while exporting only MealsFavTabNavigator ie. tab based is exported but still stack based navigation is also applied as it is nested in MealsFavTabNavigator.

### Adding Icons to TabBar
```
  Meals: {
        screen: MealsNavigator, navigationOptions: {
            tabBarLabel:'Meals',
            tabBarIcon: (tabInfo) => {
                return <Ionicons name='ios-restaurant' size={25} color={tabInfo.tintColor} />
            }
        }
    }},
    {
        tabBarOptions: {
            activeTintColor: Colors.accentColor
        }
    }
```

### Adding MaterialBottomTabs (Android Specific)
```
npm install --save react-navigation-material-bottom-tabs
npm install --save react-native-paper
```
Use the same configurations as used above and using platform check render  
``` 
 createMaterialBottomTabNavigator(__tabconfig__, {
            activeColor: 'white', #not activeTintColor
            shifting: true
        }) or createBottomTabNavigator()
```
### Adding SideDrawer
Install react-navigation-drawer
```
	npm install --save react-navigation-drawer
```
```
const MainNavigator = createDrawerNavigator({
    MealsFavs: MealsFavTabNavigator,
    Filters: filtersNavigator
})
export default createAppContainer(MainNavigator);
```

In NavitationOptions of corresponding screen
```
FavoritesScreen.navigationOptions = navData => {
    return {
        headerTitle: 'Your favorites',
        headerLeft: () => (
            <HeaderButtons HeaderButtonComponent={HeaderButton} >
                <Item title="Menu" iconName="ios-menu" onPress={() => {
                    navData.navigation.toggleDrawer()
                }} />
            </HeaderButtons>
        )
    }
};
```

### Format Side Drawer 
In the second parameter for createDrawerNavigator use
```
    {
        contentOptions: {
            activeTintColor: Colors.accentColor,
            labelStyle: {
                fontFamily: 'open-sans-bold'
            }
        }
    }
```

### Using Switch
```
            <Switch
                trackColor={{ true: Colors.primaryColor }}
                thumbColor={Platform.OS === 'android' ? Colors.primaryColor : ''}
                value={props.state}
                onValueChange={props.onChange}
            />
```

### Adding Icons to side drawer
In createStackNavigator use:
```
	const orderNavigator = createStackNavigator({
		orders:OrdersScreen},
		{
		navigationOptions: {
		drawerIcon: drawerConfig=>(
		<Ionicons name = 'md-create'  color={drawerConfig.tintColor}/>
		)
		}})
```