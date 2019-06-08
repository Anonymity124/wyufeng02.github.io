---
layout: post
title:  一个Flutter Widget显示一排Material Chips
tag: Chips, Material Design, Widgets
date: 2019-06-08
---

 

## [查看Github/callstackincubator/flutter-sorted-chips-row](http://github.com/callstackincubator/flutter-sorted-chips-row)
## [立即下载 ️⬇️ ](https://codeload.github.com/callstackincubator/flutter-sorted-chips-row/zip/master) 


 
![](https://flutterawesome.com/content/images/2019/04/sorted_chips_row.jpg)
 
>
> 用于渲染一排Material“Chip”按钮的Flutter库，它根据给定的函数进行排序。
>

 
# sorted_chips_row

A Flutter Widget displaying a row of [Material Chips](https://material.io/design/components/chips.html), sorted according to the provided comparison function.

![sorted chips row](https://static.callstack.com/assets/sorted_chips_row.gif)

## How to use

### Adding dependency

#### Regular

Add the following dependency to your `pubspec.yaml` file:

```
 dependencies:
   sorted_chips_row: ^0.1.0
```

You can read more about adding pub dependencies in [Dart documentation](https://www.dartlang.org/tools/pub/dependencies).

#### Bleeding edge

You can also depend on the code from the GitHub repository. To add this package as a dependency from git, add the following under `dependencies` section in your `pubspec.yaml`:

```
  sorted_chips_row:
    git:
      url: https://github.com/callstackincubator/flutter-sorted-chips-row.git
```

By default this dependency will get upgraded whenever a new version is being pushed to the `master` branch. To avoid that, we recommend that you also specify a ref pointing to a commit you verified:
```
      ref: COMMIT_ID
```

For details see the [Dart documentation on Git dependencies](https://www.dartlang.org/tools/pub/dependencies#git-packages)

### Using in code

The main widget class in this package is [`SortedChipsRow`](https://github.com/callstackincubator/flutter-sorted-chips-row/blob/master/lib/src/sorted_chips_row.dart). See the [library's main file](https://github.com/callstackincubator/flutter-sorted-chips-row/blob/master/lib/sorted_chips_row.dart) for usage example.  

## Getting Started with Flutter

This project is a starting point for a Dart [package](https://flutter.dev/developing-packages/), a library module containing code that can be shared easily across multiple Flutter or Dart projects.

For help getting started with Flutter, view the [online documentation](https://flutter.dev/docs), which offers tutorials,  samples, guidance on mobile development, and a full API reference.

