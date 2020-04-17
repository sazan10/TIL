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
Wrapping all contents here in App.js with SafeAreaView instead of normal View and applying style to it.
	
	
  