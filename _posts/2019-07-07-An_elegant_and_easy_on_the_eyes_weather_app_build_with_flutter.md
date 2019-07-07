---
layout: post
title:  flutter 天气应用程序 
tag: [flutter, Weather, Apps, Templates]
date: 2019-07-07
---

 


## [立即下载 ️⬇️ ](https://codeload.github.com/LonelyCpp/flutter_weather/zip/master) 


 
![](https://flutterawesome.com/content/images/2019/06/Flutter-Weather.jpg)
 
>
> 用于查看当前天气状态的Flutter应用程序。
>

 
# Flutter Weather

A Flutter application to view current weather status.
This is my first project on my journey to learning and understanding flutter and dart.

![android](./screenshots/android.png?raw=true 'android')
![ios](./screenshots/ios.gif?raw=true 'ios')
![ios](./screenshots/ios_chart.gif?raw=true 'ios')

## Features
- :white_check_mark: Beautiful minimal UI
- :white_check_mark: Dark and Light themes
- :white_check_mark: Current temperature, max and min temperature, sunset, sunrise
- :white_check_mark: Custom icons for each weather condition
- :white_check_mark: 5 day forecast
- :white_check_mark: Beautifully animated transitions
- :white_check_mark: BLoC pattern for API calls
- :white_check_mark: Line graph to show temperature variance

## Getting Started

### Prerequisites
**Flutter**
- [Flutter documentation](https://flutter.dev/docs)
- [Lab: Write your first Flutter app](https://flutter.dev/docs/get-started/codelab)
- [Cookbook: Useful Flutter samples](https://flutter.dev/docs/cookbook)


### Installing

**API Key**

Create a file called `api_keys.dart` in `lib/src/api/`

Make a class called `ApiKey` with your openweathermaps API key in it. Get it [here](https://openweathermap.org/api)

eg:
  ```
  class ApiKey {
    static const OPEN_WEATHER_MAP = 'your_key';
  }
  ```

## todo
- i18n support for multiple languages

## Acknowledgments

* [Weather Icon Pack](https://erikflowers.github.io/weather-icons/)


## Github主页 👉[LonelyCpp/flutter_weather](http://github.com/LonelyCpp/flutter_weather)