# react-native-smart-security-text
A smart security text for React Native apps, written in JS for cross-platform support.
It works on iOS and Android.

This component is compatible with React Native 0.25 and newer.

## Preview

![react-native-smart-security-text-preview-ios][1]
![react-native-smart-security-text-preview-android][2]

## Installation

```
npm install react-native-smart-security-text --save
```

## Usage

Install the button from npm with `npm install react-native-smart-security-text --save`.
Then, require it from your app's JavaScript files with `import SecurityText from 'react-native-smart-security-text'`.

```js
import React, {
    Component,
} from 'react'
import {
    View,
    Text,
    Image,
} from 'react-native'

import SecurityText from 'react-native-smart-security-text'
import Button from 'react-native-smart-button'

import image_eye_open from '../images/eye_open.png'
import image_eye_close from '../images/eye_close.png'

export default class SecurityTextDemo extends Component {

    // 构造
      constructor(props) {
        super(props)
        // 初始状态
        this.state = {
            isSecurity: false,
        }
      }

    render() {
        return (
            <View style={{marginTop: 64, flex: 1, justifyContent: 'center', alignItems: 'center', backgroundColor: '#fff',}}>
                <Button
                    style={{margin: 10, justifyContent: 'center', height: 40, justifyContent: 'center',}}
                    onPress={this._onSecurityChange}
                >
                    <Image source={this.state.isSecurity ? image_eye_close : image_eye_open} style={{width: 40, height: 40, marginRight: 3, }}/>
                </Button>
                <SecurityText
                    securityOptions={{
                        isSecurity: this.state.isSecurity,
                        startIndex: 3,
                        endIndex: 7,
                    }}
                    style={{margin:10, fontSize: 16, color: 'red',}}>
                    15912390987
                </SecurityText>
                <SecurityText
                    securityOptions={{
                        isSecurity: this.state.isSecurity,
                        startIndex: 0,
                        endIndex: 1,
                    }}
                    style={{margin:10, fontSize: 16, color: 'red',}}>
                    15912390987
                </SecurityText>
                <SecurityText
                    securityOptions={{
                        isSecurity: this.state.isSecurity,
                        startIndex: 0,
                        endIndex: 12,
                    }}
                    style={{margin:10, fontSize: 16, color: 'red',}}>
                    15912390987
                </SecurityText>
                <SecurityText
                    securityOptions={{
                        isSecurity: this.state.isSecurity,
                        startIndex: 11,
                        endIndex: 12,
                    }}
                    style={{margin:10, fontSize: 16, color: 'red',}}>
                    15912390987
                </SecurityText>
                <SecurityText
                    securityOptions={{
                        isSecurity: this.state.isSecurity,
                        startIndex: -7,
                        endIndex: -3,
                    }}
                    style={{margin:10, fontSize: 16, color: 'red',}}>
                    15912390987
                </SecurityText>
                <SecurityText
                    securityOptions={{
                        isSecurity: this.state.isSecurity,
                        length: 4,
                    }}
                    style={{margin:10, fontSize: 16, color: 'red',}}>
                    username
                </SecurityText>
                <SecurityText
                    securityOptions={{
                        isSecurity: this.state.isSecurity,
                        length: 10,
                    }}
                    style={{margin:10, fontSize: 16, color: 'red',}}>
                    address
                </SecurityText>
            </View>
        )
    }

    _onSecurityChange = () => {
        let isSecurity = !this.state.isSecurity
        this.setState({
            isSecurity,
        })
    }
}
```

## Props

Prop                         | Type   | Optional | Default   | Description
---------------------------- | ------ | -------- | --------- | -----------
...Text.propTypes            |        | Yes      |           | see [react-native documents][3]
securityOptions              | shape  | Yes      | {}        |
securityOptions.isSecurity   | bool   | Yes      | false     | when the value is true, origin text will be replaced with security text
securityOptions.startIndex   | number | Yes      | 0         | determines the startIndex of security text
securityOptions.endIndex     | number | Yes      |           | determines the endIndex of security text
securityOptions.length       | number | Yes      |           | determines the length of security text
securityOptions.securityChar | string | Yes      | '*'       | determines the securityChar of security text

[1]: http://cyqresig.github.io/img/react-native-smart-security-text-preview-ios-v1.0.0.gif
[2]: http://cyqresig.github.io/img/react-native-smart-security-text-preview-android-v1.0.0.gif
[3]: https://facebook.github.io/react-native/docs/text.html
