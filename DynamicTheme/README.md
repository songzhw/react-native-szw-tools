# Dynamic-Style/Theme

## Pain Point of React Native StyleSheet
```javascript
const styles = StyleSheet.create({
  text: {
    color: 'red',
    fontSize: 20
  }
})
```

The styles in the React Native (like the above style) are static, and are not flexible at all. You can not add `${color}`, and you can not pass in another theme either.


So this library try to build a tool to help you achieve these two golas with a minimum code:
* support pass in variables
* support pass in different theme

## How to use this library?
