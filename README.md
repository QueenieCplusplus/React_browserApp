# React_browserApp
open browser to surf Google Search Engine

# expo install

  $ expo install expo-web-browser
  
# Codebase

    import React, { Component } from 'react';
    import { Button, Text, View } from 'react-native';
    import * as WebBrowser from 'expo-web-browser';

    export default class App extends Component {
      state = {
        result: null,
      };

      render() {
        return (
          <View>
            <Button title="Open WebBrowser" onPress={this._pressHandler} />
            <Text>{this.state.result && JSON.stringify(this.state.result)}</Text>
          </View>
        );
      }

      _pressHandler = async () => {
        let result = await WebBrowser.openBrowserAsync('https://www.google.com/');
        this.setState({ result });
      };
    }
