---
layout: post
title:  适用于iOS和Android的Flutter软件包，用于显示密码输入屏幕
tag: [flutter, Password, Input]
date: 2019-07-07
---

 


## [立即下载 ️⬇️ ](https://codeload.github.com/xPutnikx/flutter-passcode/zip/master) 


 
![](https://flutterawesome.com/content/images/2019/06/Passcode-Lock-Screen.gif)
 
>
> 适用于iOS和Android的Flutter软件包，用于显示密码输入屏幕，类似于Native iOS。
>

 
[![Pub](https://img.shields.io/pub/v/passcode_screen.svg)](https://pub.dartlang.org/packages/passcode_screen) 

# Flutter - Passcode Lock Screen

A Flutter package for iOS and Android for showing passcode input screen, similar to Native iOS.

<img src="https://github.com/xPutnikx/flutter-passcode/blob/master/example/passcode-screen-demo.gif?raw=true" alt="passcode-screen-demo.gif" width="300"/>

## Installation

First add `passcode_screen` as a [dependency in your pubspec.yaml file](https://flutter.io/platform-plugins/).

Then use import

```dart
import 'package:passcode_screen/passcode_screen.dart';
```

## What can it do for you?

<img src="https://github.com/xPutnikx/flutter-passcode/blob/master/example/passcode-screen-default.png?raw=true" alt="passcode-screen-default.png" width="300"/>

1. Create a beautiful passcode lock view simply.

```dart
PasscodeScreen(
  title: title,
  passwordEnteredCallback: _onPasscodeEntered,
  cancelLocalizedText: 'Cancel',
  deleteLocalizedText: 'Delete',
  shouldTriggerVerification: _verificationNotifier.stream,  
);
```

2. Passcode input completed callback.
```dart
_onPasscodeEntered(String enteredPasscode) {
  
}
```

3. Notify passcode screen if passcode correct or not 
```dart
final StreamController<bool> _verificationNotifier = StreamController<bool>.broadcast();

_onPasscodeEntered(String enteredPasscode) {
  bool isValid = '123456' == enteredPassword;
  _verificationNotifier.add(isValid);
}

```

Don't forget to close a stream
```dart
@override
void dispose() {
  _verificationNotifier.close();
  super.dispose();
}

```

4. Customize UI.

Customize circles
```dart
class CircleUIConfig {
  final Color borderColor;
  final Color fillColor;
  final double borderWidth;
  final double circleSize;
  double extraSize;
}
```

Customize keyboard
```dart
class KeyboardUIConfig {
  final double digitSize;
  final TextStyle digitTextStyle;
  final TextStyle deleteButtonTextStyle;
  final Color primaryColor;
  final Color digitFillColor;
  final EdgeInsetsGeometry keyboardRowMargin;
  final EdgeInsetsGeometry deleteButtonMargin;
}
```

<img src="https://github.com/xPutnikx/flutter-passcode/blob/master/example/passcode-screen-custom.png?raw=true" alt="passcode-screen-custom.png" width="300"/>

### iOS & Android

Plugin is totally platform agnostic. No configuration required - the plugin should work out of the box.

## Contributions
Warmly welcome to submit a pull request!

## Passcode Lock Screen
Passcode Lock Screen is owned and maintained by [Redeyes Dev](http://redeyes-dev.com)

### Used in production
[Passkeep - Passwords Keeper](http://bit.ly/andpasskeep) 

### Contributors 

[Vladimir Hudnitsky](https://github.com/xPutnikx) 
[BeDaut](https://github.com/BeDaut)
[mix1009](https://github.com/mix1009)

## Relase notes:
### 1.0.0+1: 
Basic implementation of a widget.
- You could show a widget, enter passcode and validate it.

 ### 1.0.1
- Added `isValidCallback` to help you handle success scenario. `isValidCallback` will be invoked after passcode screen will pop.

### 1.0.2
- Added configurable background and title color. (by @BeDaut)
- Added `cancelCallback` to react when user cancelled widget (by @mix1009)

## Github主页 👉[xPutnikx/flutter-passcode](http://github.com/xPutnikx/flutter-passcode)