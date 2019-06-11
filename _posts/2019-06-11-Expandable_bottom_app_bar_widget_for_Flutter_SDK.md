---
layout: post
title:  可扩展底部应用栏插件
tag: [Tabbar, Bottom Bar]
date: 2019-06-11
---

 


## [立即下载 ️⬇️ ](https://codeload.github.com/rIIh/expandable-bottom-bar/zip/master) 


 
![](https://flutterawesome.com/content/images/2019/05/ExpandableBottomAppB2ar.gif)
 
>
> 具有可扩展工作表的可动画底部应用栏。
>

 
# ExpandableBottomAppBar

Animatable bottom app bar with expandable sheet

## Preview

<img src="https://github.com/rIIh/expandable-bottom-bar/raw/master/showcase.gif" height="650"/>

## Getting Started

Add the plugin:

```yaml
dependencies:
  ...
  expandable_bottom_bar: any
```

## Basic Usage

Adding the widget

```dart
bottomNavigationBar: BottomExpandableAppBar(
        // Provide the bar controller in build method or default controller as ancestor in a tree 
        controller: bbc,
        expandedHeight: expandedHeight.value,
        horizontalMargin: 16,
        expandedBackColor: Theme.of(context).backgroundColor,
        // Your bottom sheet code here
        expandedBody: Center(
          child: Text("Hello world!"),
        ),
        // Your bottom app bar code here
        bottomAppBarBody: Padding(
          padding: const EdgeInsets.all(8.0),
          child: Row(
            mainAxisSize: MainAxisSize.max,
            children: <Widget>[
              Expanded(
                child: Text(
                  "Hello",
                  textAlign: TextAlign.center,
                ),
              ),
              Spacer(
                flex: 2,
              ),
              Expanded(
                child: Text(
                  "World",
                  textAlign: TextAlign.center,
                ),
              ),
            ],
          ),
        ),
      )
```

## Customization (Optional)

### BottomExpandableAppBar

**horizontalMargin** - distance of sheet's sides from edge<br/>
**bottomOffset** - distance of top sheet's edge from top appbar's edge in closed state<br/>
**shape** - notch shape for FAB<br/>
**appBarHeight** - if you need change app bar height<br/>

**bottomAppBarColor** - background color of appbar container<br/>
or
**appBarDecoration** - decoration of appbar container<br/>

**expandedBackColor** - background color of sheet container<br/>
or
**expandedDecoration** - decoration of sheet container<br/>

## Controls

### BottomAppBarController

#### settings

**snap** - if true sheet will snap to opened and closed state<br/>
**dragLength** - distance that pointer should travel for fully open/close the sheet<br/>

#### callbacks

*Should have dragLength defined*<br/>
**onDrag** - use that with GestureDetector for swipe control<br/>
**onDragEnd** - use that with GestureDetector for swipe control<br/>

**open** - switch the sheet to closed state<br/>
**close** - switch the sheet to opened state<br/>
**swap** - if sheet is opened closes the sheet and vice versa<br/>

## Github主页 👉[rIIh/expandable-bottom-bar](http://github.com/rIIh/expandable-bottom-bar)