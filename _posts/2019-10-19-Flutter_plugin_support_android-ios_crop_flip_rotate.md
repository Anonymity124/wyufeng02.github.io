---
layout: post
title:  Flutter plugin support android-ios crop flip rotate
tag: [flutter代码库, Images, Cropper]
date: 2019-10-19
---

 


## [立即下载 ️⬇️ ](https://codeload.github.com/fluttercandies/flutter_image_editor/zip/master) 


 
![](https://flutterawesome.com/content/images/2019/10/flutter_image_editor.jpg)
 
>
> Support android ios, use the native way to flip, crop, rotate pictures.
>

 
# image_editor

![CI](https://github.com/fluttercandies/flutter_image_editor/workflows/CI/badge.svg)

Support android ios, use the native way to flip, crop, rotate pictures.

The version of readme pub and github may be inconsistent, please refer to [github](https://github.com/fluttercandies/flutter_image_editor).

- [image_editor](#imageeditor)
  - [Screenshot](#screenshot)
  - [Usage](#usage)
    - [ImageEditor method params](#imageeditor-method-params)
    - [ImageEditorOption](#imageeditoroption)
    - [Option](#option)
      - [Flip](#flip)
      - [Clip](#clip)
      - [Rotate](#rotate)
    - [OutputFormat](#outputformat)
  - [LICENSE](#license)

## Screenshot

![img](https://github.com/kikt-blog/image/raw/master/github/flutter_image_editor_ss.gif)

## Usage

[![pub package](https://img.shields.io/pub/v/image_editor.svg)](https://pub.dev/packages/image_editor) [![GitHub](https://img.shields.io/github/license/fluttercandies/flutter_image_editor.svg)](https://github.com/fluttercandies/flutter_image_editor) [![GitHub stars](https://img.shields.io/github/stars/fluttercandies/flutter_image_editor.svg?style=social&label=Stars)](https://github.com/fluttercandies/flutter_image_editor)

Import

```dart
import 'package:image_editor/image_editor.dart';
```

Method list:

```dart
ImageEditor.editImage();
ImageEditor.editFileImage();
ImageEditor.editFileImageAndGetFile();
ImageEditor.editImageAndGetFile();
```

[Example used alone](https://github.com/CaiJingLong/flutter_image_editor/blob/master/example/lib/advanced_page.dart)

[Example](https://github.com/CaiJingLong/flutter_image_editor/blob/master/example/lib/advanced_page.dart) of [extended_image](https://github.com/fluttercandies/extended_image)

### ImageEditor method params

| Name              | Description                            |
| ----------------- | -------------------------------------- |
| image             | dart.typed_data.Uint8List              |
| file              | dart.io.File                           |
| imageEditorOption | flutter_image_editor.ImageEditorOption |

### ImageEditorOption

```dart
final editorOption = ImageEditorOption();
editorOption.addOption(FlipOption());
editorOption.addOption(ClipOption());
editorOption.addOption(RotateOption());

editorOption.outputFormat = OutputFormat.png(88);
```

### Option

#### Flip

```dart
FlipOption(horizontal:true, vertical:false);
```

#### Clip

```dart
ClipOption(x:0, y:0, width:1920, height:1920);
```

#### Rotate

```dart
RotateOption(degree: 180);
```

### OutputFormat

```dart
var outputFormat = OutputFormat.png();
var outputFormat = OutputFormat.jpeg(95);
```

## LICENSE

MIT Style.

## Github主页 👉[fluttercandies/flutter_image_editor](http://github.com/fluttercandies/flutter_image_editor)