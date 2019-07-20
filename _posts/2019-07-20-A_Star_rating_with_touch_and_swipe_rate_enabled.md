---
layout: post
title:  已启用触摸和滑动率的星级评级
tag: [flutter代码库, Rating]
date: 2019-07-20
---

 


## [立即下载 ️⬇️ ](https://codeload.github.com/thangmam/smoothratingbar/zip/master) 


 
![](https://flutterawesome.com/content/images/2019/07/fullrating-1.gif)
 
>
> 已启用触摸和滑动率的星级评级。
>

 

A Star rating with touch and swipe rate enabled
* Supports half rate and full rate (1.0 or 0.5)
* Swipe for incrementing/decrementing rate amount
* Change star body and boundary colors independently
* Control size of the star rating
* Set your desired total Star count
* Supports click-to-rate
* Spacing between stars

## Getting Started

In your flutter project add the dependency:
```
    dependencies:
        ...
        smooth_star_rating: 1.0.3
```

## Usage example
``` 
import 'package:smooth_star_rating/smooth_star_rating.dart'; 
``` 

```java 
SmoothStarRating(
          allowHalfRating: false,
          onRatingChanged: (v) {
            rating = v;
            setState(() {});
          },
          starCount: 5,
          rating: rating,
          size: 40.0,
          color: Colors.green,
          borderColor: Colors.green,
          spacing:0.0
        )
```

## Constructor parameters
``` 
allowHalfRating                 -   Whether to use whole number for rating(1.0  or 0.5)
onRatingChanged(int rating)     -   Rating changed callback
starCount                       -   The maximum amount of stars
rating                          -   The current value of rating
size                            -   The size of a single star
color                           -   The body color of star
borderColor                     -   The border color of star
spacing                         -   Spacing between stars(default is 0.0)
```

### Screenshots

#### Full Rating
![alt text](https://raw.githubusercontent.com/thangmam/smoothratingbar/master/screenshots/fullrating.gif "Full rating")

#### Half Rating

![alt text](https://raw.githubusercontent.com/thangmam/smoothratingbar/master/screenshots/halfrating.gif  "Half Rating")
## Github主页 👉[thangmam/smoothratingbar](http://github.com/thangmam/smoothratingbar)