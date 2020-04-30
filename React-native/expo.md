### Adding fonts 
```
	npm install --save expo-font
```

In App.js
```
	import * as Font from 'expo-font';
	import {AppLoading} from 'expo';
	const fetchFonts =()=>{
		Font.loadAsync({
			'open-sans': require('path'),
			'open-sans-bold': require('path')
			})}
	export default function App(){
		const[dataLoaded, setDataLoaded] = useState(false);
		if(!dataLoaded){
			return <AppLoading startAsync ={fetchFonts} onFinish={()=> setDataLoaded(true)} />
			}
		# else render other components
		
		#using the font, in stylesheet
		title:{
			fontFamily:'open-sans-bold' #should be same as on loaded
```
		
###  Creating Global STyles
2 ways:
* Create a custom component with styling and use it everywhere eg. bodyText with custom font, size and use <BodyText>
* Create a global stylesheet, export it and apply it in every elements
```
	import { StyelSheet } from 'react-native';
	export default StyleSheet.create({
	 ...
	 })
```
### Adding Icons to buttons
```
	import {Ionicons} from '@expo/vector-icons';
	<MainButton ...>
	<Ionicons name="md-add" size={24} color="white" />
	</MainButton>
```

### Controlling Orientation
In case of login in landscape mode to prevent keyboard from overlapping the input field.
```
	<ScrollView>
		<KeyboardAvoidingView behavior="position" keyboardVerticalOffset={30}>
		...
```

### Listening to Orientation Changes
```
useEffect(() => {
    const updateLayout = () => {
      setButtonWidth(Dimensions.get('window').width / 4);
    };
  
    Dimensions.addEventListener('change', updateLayout);
    return () => {
      Dimensions.removeEventListener('change', updateLayout);
    };
 });
```
 
  
### Styling Different Platforms
```
	import {Platform } from 'react-native';
	const styles= StyleSheet.create({
	headerIOS:{...},
	headerAndroid:{}}
	
	<View style={{...styles.headerBase, ...Platform.select({ios:styles.headerIOS, android:styles.headerAndroid});
```
### Using Platform Specific code files
We can also use different codes for different platforms like MainButton.android.js and MainButton.ios.js. While importing them import  normally as import MainButton from './MainButton.js' and react-native will automatically import codes corresponding to platform.

### Using the SafeArea View
Wrapping all contents here in App.js with SafeAreaView instead of normal View and applying style to it to prevent displays in notches.

### Using Autologin
For Auto login we need to check if tokens are stored in asyncstorage in root element i.e App js but we cannot do so, as it is where redux is registered and also the starting navigator of the app also cannot be used. Hence we need to add a new navigator/screen to check if logged in and promptly send to either the app screen or the authentication screen.
```
import React, { useEffect } from 'react';
import {
  View,
  ActivityIndicator,
  StyleSheet,
  AsyncStorage
} from 'react-native';
import { useDispatch } from 'react-redux';

import Colors from '../constants/Colors';
import * as authActions from '../store/actions/auth';

const StartupScreen = props => {
  const dispatch = useDispatch();

  useEffect(() => {
    const tryLogin = async () => {
      const userData = await AsyncStorage.getItem('userData');
      if (!userData) {
        props.navigation.navigate('Auth');
        return;
      }
      const transformedData = JSON.parse(userData);
      const { token, userId, expiryDate } = transformedData;
      const expirationDate = new Date(expiryDate);

      if (expirationDate <= new Date() || !token || !userId) {
        props.navigation.navigate('Auth');
        return;
      }

      const expirationTime = expirationDate.getTime() - new Date().getTime();

      props.navigation.navigate('Shop');
      dispatch(authActions.authenticate(userId, token, expirationTime));
    };

    tryLogin();
  }, [dispatch]);

  return (
    <View style={styles.screen}>
      <ActivityIndicator size="large" color={Colors.primary} />
    </View>
  );
};

const styles = StyleSheet.create({
  screen: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center'
  }
});

export default StartupScreen;
```
```
import React, { useEffect, useRef } from 'react';
import { useSelector } from 'react-redux';
import { NavigationActions } from 'react-navigation';

import ShopNavigator from './ShopNavigator';

const NavigationContainer = props => {
  const navRef = useRef();
  const isAuth = useSelector(state => !!state.auth.token);

  useEffect(() => {
    if (!isAuth) {
      navRef.current.dispatch(
        NavigationActions.navigate({ routeName: 'Auth' })
      );
    }
  }, [isAuth]);

  return <ShopNavigator ref={navRef} />;
};

export default NavigationContainer;
```
	

  