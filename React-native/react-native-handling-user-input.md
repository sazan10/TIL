### Validation
Example for validator:
```
const validate = (val, rules, connectedValue) => {
  let isValid = true;
  for (let rule in rules) {
    switch (rule) {
      case "isEmail":
        isValid = isValid && emailValidator(val);  #&& is used since it runs on loop and incase any loop returns isValid false it will return false overall
        break;
      case "minLength":
        isValid = isValid && minLengthValidator(val, rules[rule]);
        break;
      case "equalTo":
        isValid = isValid && equalToValidator(val, connectedValue[rule]);
        break;
      default:
        isValid = true;
    }
  }
  
  return isValid;
};

const emailValidator = val => {
  return /[a-z0-9!#$%&'*+/=?^_`{|}~-]+(?:\.[a-z0-9!#$%&'*+/=?^_`{|}~-]+)*@(?:[a-z0-9](?:[a-z0-9-]*[a-z0-9])?\.)+[a-z0-9](?:[a-z0-9-]*[a-z0-9])?/.test(
    val
  );
};

const minLengthValidator = (val, minLength) => {
    return val.length >= minLength;
};

const equalToValidator = (val, checkValue) => {
    return val === checkValue;
};

export default validate;
```

Applied in Auth.js as 
```
state ={
	 controls: {
      email: {
        value: "",
        valid: false,
        validationRules: {
          isEmail: true
        }
      },
      password: {
        value: "",
        valid: false,
        validationRules: {
          minLength: 6
        }
      },
      confirmPassword: {
        value: "",
        valid: false,
        validationRules: {
          equalTo: "password"
        }
      }
    }
  };
  
   updateInputState = (key, value) => {
    let connectedValue = {};
    if (this.state.controls[key].validationRules.equalTo) {
      const equalControl = this.state.controls[key].validationRules.equalTo;
      const equalValue = this.state.controls[equalControl].value;
      connectedValue = {
        ...connectedValue,
        equalTo: equalValue
      };
    }
    if (key === "password") { #needed because after matching confirm password with password valid is true but on changing only passwoord still returns true so it should be checked for password as well --1
      connectedValue = {
        ...connectedValue,
        equalTo: value
      };
    }
    this.setState(prevState => {
      return {
        controls: {
          ...prevState.controls,
          confirmPassword: { # need to update confirm password first 
            ...prevState.controls.confirmPassword,
            valid:
              key === "password" #same as 1, only check for password
                ? validate(
                    prevState.controls.confirmPassword.value,
                    prevState.controls.confirmPassword.validationRules,
                    connectedValue
                  )
                : prevState.controls.confirmPassword.valid # leave as it is 
          },
          [key]: { # now it overrides confirmpassword if the current state is confirmpassword else confirmpassword key is not accessed.
            ...prevState.controls[key],
            value: value,
            valid: validate(
              value,
              prevState.controls[key].validationRules,
              connectedValue
            )
          }
        }
      };
    });
  };

```

### Feedback on invalidity
Create a stylesheet as:
```
	invalid:{
		backgroundColor :'shadeofred',
		borderColor: "red"
		}
	<TextInput style={[styles.input, props.style, props.valid, !props.valid && props.touched? styles.invalid:null]}}/> #props.valid? null:styles.invalid, if touched is not used
```
In component where the input is created:
```
<DefaultInput ....... valid={this.state.controls.confirmPassword.valid} 
  touched={this.state.controls.inputfieldname.touched}/>
```
valid is made true onChangeTextHandler as shown above. Also to remove the effects on initial load, create a state 'touched' for each input field(false) and return true onChangeTextHandler for each input field and performs checks as suggested above.

### Handling Keyboard for Input
Ref: https://reactnative.dev/docs/textinput.html
```
	<DefaultInput 
		...
		autoCapitalze={false}
		autoCorrect = {false}
		secureTextEntry
		key boardType="email-address"
		/>
```

### Auto adjusting keyboard to uncover inputfields
Wrap with
```
	<KeyboardAvoidingView style={styles.container} behavior="padding"/>
```

### Close keyboard on pressing outside the field
```
	<TouchableWIthoutFeedback onPress={Keyboard.dismiss} >
```
However, it could not wrap around ImageBackground or KeyboardAvoidingView earlier
	
