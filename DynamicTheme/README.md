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
Here is a complete example to use it:

```typescript
export const DynamicStyleRulesDemo = (props: IProps) => {
  const rawStyles = (params: any, theme: any) => ({
    text: {
      fontSize: params.fontSize * 2,
      color: theme.text.title.color
    },
    image: {
      width: params.imgSize,
      height: params.imgSize
    }
  });
  const styles = parseStyle(rawStyles, props, NormalTheme);

  return (
    <View>
      <Text style={styles.text}> 动态样式 </Text>
      <Image style={styles.image} source={require("../../../res/images/category_app.png")}/>
    </View>
  );
};
```

1. The rawStyles is a function.
And you pass it to the `parseStyle(func, styleProps, theme)`, so you could get a style for React native.

2. The `NormalTheme` could be also a `DarkTheme`, or `AnotherDifferentTheme`. You could list the themes in your own file. 
And here is the definition of such a theme:

```javascript
export const NormalTheme = {
  text: {
    title: {
      color: "green"
    }
  }
};

```
