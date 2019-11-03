---
layout: post
title:  A Flutter internationalized strings generator
tag: [I18n]
date: 2019-11-03
---

 


## [DOWNLOAD ️⬇️ ](https://codeload.github.com/smartnsoft/FlappyTranslator/zip/master) 


 
![](https://flutterawesome.com/content/images/2019/10/flappy_translator.jpg)
 
>
> A Flutter internationalized strings generator. The idea is to automate the static Strings generation from a CSV file.
>

 
# flappy_translator

A Flutter internationalized strings generator.
The idea is to automate the static Strings generation from a CSV file.
This way, anybody could make a CSV file with all the translations and automatically generate corresponding Dart code.


## Getting Started

In order to use the flappy_translator package, you will have to provide your translatinos in a CSV file (formatted with comma separator).

### Create a CSV and export it in "comma separated" format

Here is our CSV example :
![alt text](https://github.com/smartnsoft/FlappyTranslator/blob/master/documentation/csv_example.png "Example of CSV")

*exported file myFile.csv*

```
keys,fr,en,es
appTitle,Ma super application,My awesome application,Mi gran application
subtitle,Un sous titre,A subtitle,Un subtitulò
description,Un texte avec une variable : %1$s,A text with a variable : %1$s,Un texto con una variable : %1$s
littleTest,"Voici, pour l'exemple, ""un test"" avec la variable %age$d","Here is, for the example, ""a test"" with variable %age$d","Aqui esta, por ejemplo, ""una prueba"" con la variable %age$d"
```

### Add dependency
```
dependencies:
  flutter_localizations:
    sdk: flutter
    
dev_dependencies: 
  flappy_translator: 
```

### Run package
```
flutter pub get
flutter pub run flappy_translator test.csv path/to/destination
```

### Use the i18n generated file

The package used your CV file in order to generate a file named `i18n.dart` in `path/to/destination` you provided.

Once you have this file in your project, all you have to do is :

1. Add the I18nDelegate to your delegates

```
class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      localizationsDelegates: [
        const I18nDelegate(),
        GlobalMaterialLocalizations.delegate,
        GlobalWidgetsLocalizations.delegate,
      ],
      supportedLocales: I18nDelegate.supportedLocals,
      home: Home(),
    );
  }
}
```

2. Use your generated I18n class ! :)

```
class Home extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      body: SafeArea(
        child: Center(
          child: Column(
            children: <Widget>[
              Text(I18n.of(context).appTitle),
              Text(I18n.of(context).description(var1: 2)),
              Text(I18n.of(context).littleTest(age: 32)),
            ],
          ),
        ),
      ),
    );
  }
}
```

## Rules and functionnalities

### Default language

The `first` language's column of your CSV file will be considered as the `default`one.
That means : 

* If other languages does not have translation for specific words, it will take the corrresponding one in the default language.

* The first column must be totally filled ! It will not work otherwise.

### Handling different languages for one country

You have the possibility, since version 1.4 to write something like `de_CH`.
It will take the Swiss's German language.

### Add variables in Strings

We added the possibility to handle variables in the Strings.
This means respecting some rules : 

1. In order to be able to recognize them, you must write them this way :

* %myVariable$d (`d` stands for an int type)
* %myVariable$s (`s` stands for a String type)

2. if your variable's name start with a number, the generated name will be `varmyVariable`
Otherwise, the generated variable name would be the name you provided.

* `%1$d` becomes `var1`
* `%age$d` becomes `age`

3. Variables are optional in the generated dart code

Let's take the example of the `description` String in the CSV we used.

The generated function signature will be :

```
String description({String var1,})
```

If the variables are not provided, the String will be given without replacing the variables placeholders.



## Github HOME 👉[smartnsoft/FlappyTranslator](http://github.com/smartnsoft/FlappyTranslator)