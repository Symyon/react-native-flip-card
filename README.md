react-native-flip-card
===

> The card component which have motion of flip for React Native(iOS/Android)

[![NPM](https://nodei.co/npm/react-native-flip-card.png?downloads=true&downloadRank=true&stars=true)](https://nodei.co/npm/react-native-flip-card/)

[![npm](https://img.shields.io/npm/v/react-native-flip-card.svg)]()[![npm](https://img.shields.io/npm/l/react-native-flip-card.svg)]()

[![js-standard-style](https://cdn.rawgit.com/feross/standard/master/badge.svg)](https://github.com/feross/standard) [![forthebadge](http://forthebadge.com/images/badges/uses-js.svg)](http://forthebadge.com)

Demo
---
![](./doc/ver3_android_demo.gif)


Installation
==

in Cli
---
```
npm i react-native-flip-card
```


Usage
===

Simple
---
```
import FlipCard from 'react-native-flip-card'

<FlipCard>
  {/* Face Side */}
  <View style={styles.face}>
    <Text>The Face</Text>
  </View>
  {/* Back Side */}
  <View style={styles.back}>
    <Text>The Back</Text>
  </View>
</FlipCard>
```

Customized
---
```
<FlipCard
  style={styles.card}
  friction={6}
  perspective={1000}
  flipHorizontal={true}
  flipVertical={false}
  flip={false}
  clickable={true}
  onFlipEnd={(isFlipEnd)=>{console.log('isFlipEnd', isFlipEnd)}}
  //other custom props include: customAnimation, contentSwitchTime, flipInputRange, flipOutputRange
>
  {/* Face Side */}
  <View style={styles.face}>
    <Text>The Face</Text>
  </View>
  {/* Back Side */}
  <View style={styles.back}>
    <Text>The Back</Text>
  </View>
</FlipCard>
```

Props
===

flip(bool) `Default: false`
---
If you change default display side, you can set `true` to this param. If you change side, you can pass `bool` variable dynamically.

clickable(bool) `Default: true`
---
If you want to disable click a card, you can set `false` to this param.

friction(number) `Default: 6`
---
The friction of card animation

perspective(number) `Default: 0`
---
The amount of perspective applied to the flip transformation

flipHorizontal(bool) `Default: false`
---
If you set true, a card flip to horizontal.

![](./doc/ver2_horizontal.gif)


flipVertical(bool) `Default: true`
---
If you set false, a card not flip to vertical. If you set true both `flipHorizontal` and `flipVertical` , a card flip to diagonal.


vertical | diagnoal
---- | ----
 ![](./doc/ver2_vertical.gif)| ![](./doc/ver2_diagonal.gif)

onFlipStart(function) `(isFlipStart) => {}`
---
When a card starts a flip animation, call `onFlipEnd` function with param.

onFlipEnd(function) `(isFlipEnd) => {}`
---
When a card finishes a flip animation, call `onFlipEnd` function with param.

alignHeight(boolean) `Default:false`
---
If you pass `true` to `alignHeight` param, the card keep height of bigger side.

alignWidth(boolean) `Default:false`
---
If you pass `true` to `alignWidth` param, the card keep width of bigger side.

useNativeDriver(boolean) `Default:false`
---
If you pass `true` to `useNativeDriver` param, the card animation will utilize the native driver.

customAnimation(function) `Default:Animated.spring`
---
Customize the animation applied on the rotation angle. This function takes two arguments:
 - `value`: the value to animate
 - `toValue`: the final value at the end of the animation

**Example:** for a 200ms linear animation, `customAnimation={(value, toValue) => Animated.timing(value, { toValue, duration: 200, useNativeDriver: true })}`

contentSwitchTime(number) `Default:120`
---
If you use a custom animation, the content fliping time should be adjusted due to custom animation time or the custom animation curve, which may not be symetrical. Default 120 was kept in case you use the default spring animation.

flipInputRange(arrayOf(number))
---
Give a custom input, usefull if you want to split the input in intervals, like jumping some angles

flipOutputRange(arrayOf(number))
---
Give a custom output, usefull if you want to fplit the card to a certain angle or split the ouput in intervals, like jumping some angles


Credits
===
Inspired by [react-flipcard](https://github.com/mzabriskie/react-flipcard)


License
===
MIT

