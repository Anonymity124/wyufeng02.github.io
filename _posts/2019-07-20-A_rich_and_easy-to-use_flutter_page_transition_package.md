---
layout: post
title:  丰富且易于使用的flutter页面转换包
tag: [flutter, Transitions]
date: 2019-07-20
---

 


## [立即下载 ️⬇️ ](https://codeload.github.com/handoing/flutter_page_transition/zip/master) 


 
![](https://flutterawesome.com/content/images/2019/07/flutter_page_transition.jpg)
 
>
> 
>

 
# flutter_page_transition

A rich, convenient, easy-to-use flutter page transition package.

[![Version](https://img.shields.io/badge/version-0.1.4-blue.svg)](https://github.com/handoing/flutter_page_transition)

[README in Chinese](README-zh.md)

## Some Demos

![](https://raw.githubusercontent.com/handoing/flutter_page_transition/master/./screenshots/fadeIn.gif)
![](https://raw.githubusercontent.com/handoing/flutter_page_transition/master/./screenshots/slideInLeft.gif)
![](https://raw.githubusercontent.com/handoing/flutter_page_transition/master/./screenshots/slideLeft.gif)
![](https://raw.githubusercontent.com/handoing/flutter_page_transition/master/./screenshots/slideParallaxLeft.gif)
![](https://raw.githubusercontent.com/handoing/flutter_page_transition/master/./screenshots/slideZoomLeft.gif)
![](https://raw.githubusercontent.com/handoing/flutter_page_transition/master/./screenshots/transferRight.gif)
![](https://raw.githubusercontent.com/handoing/flutter_page_transition/master/./screenshots/rippleRightUp.gif)

## Getting Started

Add this to your package's pubspec.yaml file:
```yaml
dependencies:
  flutter_page_transition: ^0.1.0
```
You can also depend on this package stored in my repository:
```yaml
flutter_page_transition:
  git:
    url: git://github.com/handoing/flutter_page_transition.git
```
You should then run `flutter packages upgrade`.

## Transition Type

| Page Transition Type  | Direction |
| :- | :-|
| slideInLeft | ⬅️  |
| slideInLeft | ➡️  |
| slideInUp | ⬆️  |
| slideInDown | ⬇️  |
| slideLeft | ⬅️  |
| slideRight | ➡️  |
| slideUp | ⬆️  |
| slideDown | ⬇️  |
| slideParallaxLeft | ⬅️  |
| slideParallaxRight | ➡️  |
| slideParallaxUp | ⬆️  |
| slideParallaxDown | ⬇️  |
| slideZoomLeft | ⬅️  |
| slideZoomRight | ➡️  |
| slideZoomUp | ⬆️  |
| slideZoomDown | ⬇️  |
| rippleRightUp | ↖️ |
| rippleLeftUp | ↗️  |
| transferRight | ⬅️  |
| transferUp | ⬆️  |
| fadeIn | ❌  |
| custom | ❌  |

## Example

Use PageRouteBuilder Widget
```dart
initialRoute: 'Home',
onGenerateRoute: (RouteSettings routeSettings){
    return new PageRouteBuilder<dynamic>(
      settings: routeSettings,
      pageBuilder: (BuildContext context, Animation<double> animation, Animation<double> secondaryAnimation) {
        switch (routeSettings.name){
          case 'Home':
            return HomePage();
          case 'Other':
            return OtherPage();
          default:
            return null;
        }
      },
      transitionDuration: const Duration(milliseconds: 300),
      transitionsBuilder: (BuildContext context, Animation<double> animation,
          Animation<double> secondaryAnimation, Widget child) {
          return effectMap[PageTransitionType.slideInLeft](Curves.linear, animation, secondaryAnimation, child);
      }
    );
}

// use Navigator
Navigator.of(context).pushNamed('Other');
// or
Navigator.of(context).push(PageTransition(type: PageTransitionType.slideInLeft, child: FirstPage()));


```

Create custom methods:
```dart
transitionEffect.createCustomEffect(
  handle: (Curve curve, Animation<double> animation, Animation<double> secondaryAnimation, Widget child) {
    return new SlideTransition(
      position: new Tween<Offset>(
        begin: const Offset(1.0, 0.0),
        end: const Offset(0.0, 0.0),
      ).animate(CurvedAnimation(parent: animation, curve: curve)),
      child: child,
    );
  }
);

// use custom
effectMap[PageTransitionType.custom](Curves.linear, animation, secondaryAnimation, child);
```

## Test

run test
```bash
flutter test
```

## Test Driver

run driver test
```bash
cd example/
flutter drive --target=test_driver/app.dart
```

## License

[MIT](LICENSE)

## Github主页 👉[handoing/flutter_page_transition](http://github.com/handoing/flutter_page_transition)