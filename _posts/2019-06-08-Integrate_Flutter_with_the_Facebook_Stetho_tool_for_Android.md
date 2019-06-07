---
layout: post
title:  将Flutter与适用于Android的Facebook Stetho工具集成
tag: Dev Tools
date: 2019-06-08
---

# [将Flutter与适用于Android的Facebook Stetho工具集成 ](http://github.com/brianegan/flutter_stetho) 



## [查看Github/brianegan/flutter_stetho](http://github.com/brianegan/flutter_stetho)
## [立即下载 ️⬇️ ](https://codeload.github.com/brianegan/flutter_stetho/zip/master) 


 
![](https://flutterawesome.com/content/images/2018/11/flutter_stetho.jpg)
 
>
> 通过Stetho Android Library将Flutter连接到Android设备上的Chrome Dev Tools的插件。
>

 
# flutter_stetho

A plugin that connects Flutter to the Chrome Dev Tools on Android devices via the [Stetho Android Library](http://facebook.github.io/stetho/).

## Network Inspector

The main feature I was aiming to achieve was a Network Inspector. 

<img src="https://github.com/brianegan/flutter_stetho/raw/master/assets/network_inspector.gif" alt="Network Inspector in Action"/>

## Getting Started

How can you too get this plugin up and running in your own app? Follow these steps.

### Install the plugin  

Follow the [installation instructions on the Pub website](https://pub.dartlang.org/packages/flutter_stetho#-installing-tab-)

### Install StethoHttpOverrides

Next, you'll need to install the `Stetho.initialize()` in the main() function of your app. This will enable Stetho and allow `flutter_stetho` to wrap all http calls and report information to the Chrome Dev Tools via the Stetho package from Facebook.

Note: It's probably a good idea only put this override in [a `main_dev.dart` file](https://flutter.rocks/2018/03/02/separating-build-environments-part-one/). 

```dart
void main() {
  Stetho.initialize();

  runApp(new MyApp());
}
```

### Run your app on an Android Device

`flutter run`

### Open Chrome

Pop open Chrome or Chromium, navigate to `chrome://inspect`

You should now see your App appear in the window.

## Known Issues

  * Timing may be slightly off for some requests. That's because:
  * Code is rough mvp / prototype code. Needs improvement.
  * Animated Gifs not working
  * Some error cases may not be properly handled. Need more testing / feedback to find problems.
  * No Tests
  * If the app shuts down on start up run `flutter clean` to remove old builds.
