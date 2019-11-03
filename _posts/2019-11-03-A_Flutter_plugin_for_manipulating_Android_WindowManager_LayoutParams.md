---
layout: post
title:  A Flutter plugin for manipulating Android WindowManager LayoutParams
tag: [Layout]
date: 2019-11-03
---

 


## [DOWNLOAD ️⬇️ ](https://codeload.github.com/adaptant-labs/flutter_windowmanager/zip/master) 


 
![](https://flutterawesome.com/content/images/2019/10/flutter_windowmanagerx.jpg)
 
>
> A Flutter plugin for manipulating Android WindowManager LayoutParams dynamically at application run-time.
>

 
# flutter_windowmanager

[![Build Status](https://travis-ci.com/adaptant-labs/flutter_windowmanager.svg?branch=master)](https://travis-ci.com/adaptant-labs/flutter_windowmanager#)
[![Pub](https://img.shields.io/pub/v/flutter_windowmanager.svg)](https://pub.dartlang.org/packages/flutter_windowmanager)

A Flutter plugin for manipulating Android WindowManager LayoutParams
dynamically at application run-time.

![Example App Use](https://raw.githubusercontent.com/adaptant-labs/flutter_windowmanager/master/screenshot.jpg)

## Motivation

While Android natively supports a range of window modes, there was no
good way to set these dynamically within a running Flutter application -
instead requiring that these flags are set within the native
`MainActivity` of the Flutter application itself.

In our App, we only wished to disable screenshots for specific screens,
rather than across the entire application lifecycle. This can now be
accomplished by simply calling:

```
await FlutterWindowManager.addFlags(FlutterWindowManager.FLAG_SECURE);
```

for the relevant screen.

This can further be toggled for a specific screen by either using a
[RouteAware] mixin, or through direct toggling in `initState()` and
`dispose()` methods in the case of stateful widgets.

[RouteAware]: https://api.flutter.dev/flutter/widgets/RouteAware-class.html

## Flags

The full range of [LayoutParams] flags are passed through. The plugin
will carry out basic API level checking and throw an error on any
unsupported flag specification. Flags are implemented using a bitmask,
and may be specified individually or ORed together for setting/clearing
multiple flags at once.

The current list of flags is:

```
FLAG_ALLOW_LOCK_WHILE_SCREEN_ON
FLAG_ALT_FOCUSABLE_IM
FLAG_DIM_BEHIND
FLAG_FORCE_NOT_FULLSCREEN
FLAG_FULLSCREEN
FLAG_HARDWARE_ACCELERATED
FLAG_IGNORE_CHEEK_PRESSES
FLAG_KEEP_SCREEN_ON
FLAG_LAYOUT_INSET_DECOR
FLAG_LAYOUT_IN_SCREEN
FLAG_LAYOUT_NO_LIMITS
FLAG_NOT_FOCUSABLE
FLAG_NOT_TOUCHABLE
FLAG_NOT_TOUCH_MODAL
FLAG_SCALED
FLAG_SECURE
FLAG_SHOW_WALLPAPER
FLAG_SPLIT_TOUCH
FLAG_WATCH_OUTSIDE_TOUCH
FLAG_BLUR_BEHIND
FLAG_DISMISS_KEYGUARD
FLAG_DITHER
FLAG_DRAWS_SYSTEM_BAR_BACKGROUNDS
FLAG_LAYOUT_ATTACHED_IN_DECOR
FLAG_LAYOUT_IN_OVERSCAN
FLAG_LOCAL_FOCUS_MODE
FLAG_SHOW_WHEN_LOCKED
FLAG_TOUCHABLE_WHEN_WAKING
FLAG_TRANSLUCENT_NAVIGATION
FLAG_TRANSLUCENT_STATUS
FLAG_TURN_SCREEN_ON
```

In practice, this plugin was developed primarily for the toggling of
`FLAG_SECURE`. Other flags have not been tested, and we make no
guarantees that toggling with any of the other flags will interact well
with Flutter - if you find specific problems with any particular flag,
please let us know in the [issue tracker][tracker].

[LayoutParams]: https://developer.android.com/reference/android/view/WindowManager.LayoutParams.html

## Features and bugs

Please file feature requests and bugs at the [issue tracker][tracker].

[tracker]: https://github.com/adaptant-labs/flutter_windowmanager/issues

## License

Licensed under the terms of the Apache 2.0 license, the full version of which can be found in the
[LICENSE](LICENSE) file included in the distribution.
## Github HOME 👉[adaptant-labs/flutter_windowmanager](http://github.com/adaptant-labs/flutter_windowmanager)