### Maps
Maintained by airbnb
You will need to get the api key and add it to your project in manifest for android. Refer to:
https://github.com/react-native-community/react-native-maps
```
	npm install --save react-native-maps
```

### Adding package to ios
* Right click on library and click add Files to project/course
* Go to node modules, package name->lib-> ios->xcode
* Click on project name->resources->build phases-> link binary with libraries->click + ->search package name-click add now
* IN build settings, header search paths add as required / given in reference

### Adding a simple map
```
	state ={
		focusedLocations:{
			latitude:49545,
			longitude:23434,
			latitudeDelta:0.12,
			longitudeDelta:Dimenstions.get("window").width/Dimenstions.get("window").height*0.12
			}
		}
		<MapView initialRegion ={this.state.focusedLocation} />
```
### Picking place using onPress
```
	pickLocationHandler = event=>{
		const coords = event.nativeEvent.coordinate;
		this.setState(prevState => { 
			return {
				focusedLocation: {
					...prevState.focusedLocation,
					latitude: coords.latitude,
					longitude: coords.longitude
					}
				}
			});
	<MapView initialRegion ={this.state.focusedLocation} region ={this.state.focusedLocation} />
```

### Adding a Marker
Add a state to be true onPress in map and use:
``` 
	if(this.state.locationChosen){
		marker =<MapView.Marker coordinate={this.state.focusedLocation}}
		<MapView ...> {marker}</MapView>
```
### Animating place picking
Add ref to MapCiew
```
<MapView initialRegion ={this.state.focusedLocation} ref={ref =>this.map=ref} >
```
Dont need to add region in MapView since it will animate to position and no hardcoding of region is needed.

Then in onPress Handler
```
	const coords= event.nativeEvent.coordinate;
	this.map.animateToRegion{
		...this.state.focusedLocation,
		latitude: coords.latitude,
		longitude: coords.longitude
		}
```
### Fetching User Location
OnButton click to get user location
```
getLocationHandler=()=>{
	navigator.geolocation.getCurrentPosition(pos => {
		const coordsEvent = {
			nativeEvent: {
				coordinate:{
					latitude: pos.coords.latitude,
					longitude: pos.coords.longitude
					}
				}
			};
			this.pickLocationHandler(coordEvent); //updates location state as given above
			,
			err => {console.log(err);
			alert("Error Fetching position");}}
}
```
Also add permission
```			
	<uses-permission android:name="android.permission.ACCESS_FINE_LOCATION"/>
```

Also for ios
<ul><li>in project folder->Info.plist->right click infor property list-> add a row-> privacy location usage descriptor -> provide value(lets share a place)</ul>

### ImagePicker


				

